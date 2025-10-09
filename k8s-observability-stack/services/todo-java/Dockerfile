# Use an official OpenJDK 17 image
FROM eclipse-temurin:17-jdk

# Set working directory
WORKDIR /app

# Copy Gradle wrapper and related files first (for caching)
COPY gradlew .
COPY gradle gradle
COPY build.gradle settings.gradle ./

# Ensure wrapper is executable
RUN chmod +x gradlew

# Pre-download dependencies (better layer caching)
RUN ./gradlew dependencies --no-daemon || true

# Copy source code last (avoids invalidating cache unnecessarily)
COPY src src

# Build application without running tests
RUN ./gradlew clean build -x test --no-daemon

# Expose app port
EXPOSE 3000

# Run the built JAR
CMD ["java", "-jar", "build/libs/todo-java-0.0.1-SNAPSHOT.jar"]

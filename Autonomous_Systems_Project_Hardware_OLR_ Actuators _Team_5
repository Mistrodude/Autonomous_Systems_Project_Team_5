// Rear Motor Driver (Main Driving Motors)
#define ENA_REAR 5  // PWM for rear motors
#define IN1_REAR 8  // Rear motor direction pin 1
#define IN2_REAR 9  // Rear motor direction pin 2

// Front Motor Driver (Additional Driving Motors)
#define ENA_FRONT 3  // PWM for front motors
#define IN1_FRONT 6  // Front motor direction pin 1
#define IN2_FRONT 7  // Front motor direction pin 2

// Steering Motor Driver
#define ENB_STEERING 11 // PWM for steering motors
#define IN1_STEERING 10 // Steering motor direction pin 1
#define IN2_STEERING 12 // Steering motor direction pin 2

void setup() {
    // Set all motor pins as OUTPUT
    pinMode(ENA_REAR, OUTPUT);
    pinMode(IN1_REAR, OUTPUT);
    pinMode(IN2_REAR, OUTPUT);

    pinMode(ENA_FRONT, OUTPUT);
    pinMode(IN1_FRONT, OUTPUT);
    pinMode(IN2_FRONT, OUTPUT);

    pinMode(ENB_STEERING, OUTPUT);
    pinMode(IN1_STEERING, OUTPUT);
    pinMode(IN2_STEERING, OUTPUT);
}

void loop() {
    // Move Forward (Both Front & Rear Motors)
    digitalWrite(IN1_REAR, HIGH);
    digitalWrite(IN2_REAR, LOW);
    digitalWrite(IN1_FRONT, HIGH);
    digitalWrite(IN2_FRONT, LOW);
    analogWrite(ENA_REAR, 255); // Max speed
    analogWrite(ENA_FRONT, 255); // Max speed
    delay(2000);

    // Move Backward
    digitalWrite(IN1_REAR, LOW);
    digitalWrite(IN2_REAR, HIGH);
    digitalWrite(IN1_FRONT, LOW);
    digitalWrite(IN2_FRONT, HIGH);
    analogWrite(ENA_REAR, 255);
    analogWrite(ENA_FRONT, 255);
    delay(2000);

    // Turn Right while moving forward (4 seconds)
    digitalWrite(IN1_REAR, HIGH);
    digitalWrite(IN2_REAR, LOW);
    digitalWrite(IN1_FRONT, HIGH);
    digitalWrite(IN2_FRONT, LOW);
    digitalWrite(IN1_STEERING, HIGH);  // Steering right
    digitalWrite(IN2_STEERING, LOW);
    analogWrite(ENA_REAR, 255);
    analogWrite(ENA_FRONT, 255);
    analogWrite(ENB_STEERING, 255); // Max steering
    delay(4000);

    // Turn Left while moving **backward** (4 seconds)
    digitalWrite(IN1_REAR, LOW);
    digitalWrite(IN2_REAR, HIGH);
    digitalWrite(IN1_FRONT, LOW);
    digitalWrite(IN2_FRONT, HIGH);
    digitalWrite(IN1_STEERING, LOW);  // Steering left
    digitalWrite(IN2_STEERING, HIGH);
    analogWrite(ENA_REAR, 255);
    analogWrite(ENA_FRONT, 255);
    analogWrite(ENB_STEERING, 255);
    delay(4000);

    // Stop for 5 seconds AFTER backward left turn
    digitalWrite(IN1_REAR, LOW);
    digitalWrite(IN2_REAR, LOW);
    digitalWrite(IN1_FRONT, LOW);
    digitalWrite(IN2_FRONT, LOW);
    analogWrite(ENA_REAR, 0);
    analogWrite(ENA_FRONT, 0);
    digitalWrite(IN1_STEERING, LOW);
    digitalWrite(IN2_STEERING, LOW);
    analogWrite(ENB_STEERING, 0);
    delay(5000);

    // Turn Left while moving forward (4 seconds)
    digitalWrite(IN1_REAR, HIGH);
    digitalWrite(IN2_REAR, LOW);
    digitalWrite(IN1_FRONT, HIGH);
    digitalWrite(IN2_FRONT, LOW);
    digitalWrite(IN1_STEERING, LOW);  // Steering left
    digitalWrite(IN2_STEERING, HIGH);
    analogWrite(ENA_REAR, 255);
    analogWrite(ENA_FRONT, 255);
    analogWrite(ENB_STEERING, 255);
    delay(4000);

    // Stop Everything
    digitalWrite(IN1_REAR, LOW);
    digitalWrite(IN2_REAR, LOW);
    analogWrite(ENA_REAR, 0);

    digitalWrite(IN1_FRONT, LOW);
    digitalWrite(IN2_FRONT, LOW);
    analogWrite(ENA_FRONT, 0);

    digitalWrite(IN1_STEERING, LOW);
    digitalWrite(IN2_STEERING, LOW);
    analogWrite(ENB_STEERING, 0);

    delay(2000); // Pause before repeating
}

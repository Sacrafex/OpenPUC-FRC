# Robot Control Documentation
We are looking for contributors! Please make a pull request if you have additions.

## Definitions

- **Syntax**: The way something is written
- **Variable**: A value stored in the computer
- **Axis**: A line about which something rotates

## Variable Types

### Access Modifiers
- `Private` - Restricts to only within the same class
- `Protected` - Same packages and subclasses
- `Default` - Only within the same package
- `Public` - All open

### Other Keywords
- `Final` - A variable that cannot change after initialization
- `Static` - Shared by all instances
- `Abstract` - Cannot be instantiated and has no implementation

## Controls

### Axis Controls

**Syntax Example**:  
`private final int translationAxis = XboxController.Axis.kLeftY.value;`

**Explanation**:  
We create a new variable called `translationAxis` and set it to the value of the Xbox controller's left thumbstick Y axis. This can be called later to fetch the value and plug into a function.

**Different Types**:
- `kLeftY` - Left Thumbstick, Y Axis
- `kLeftX` - Left Thumbstick, X Axis
- `kRightY` - Right Thumbstick, Y Axis
- `kRightX` - Right Thumbstick, X Axis
- `kLeftTrigger` - Left Trigger Button
- `kRightTrigger` - Right Trigger Button

**Called by**:  
`XboxController.Axis.[InsertType].value`

### Button Controls

**Syntax Example**:  
`private final JoystickButton zeroGyro = new JoystickButton(driver, XboxController.Button.kY.value);`

**Explanation**:  
We create a new variable called `zeroGyro` and set it to the action of making a new Joystick button and fetching the value. This can be called later to fetch the value and plug it into a function.

**Different Types**:
- `kY` - Y Button
- `kB` - B Button
- `kA` - A Button
- `kX` - X Button
- `kStart` - Start Button
- `kLeftBumper` - Left Bumper
- `kRightBumper` - Right Bumper

**Called by**:  
`new JoystickButton(driver, XboxController.Button.[InsertType].value)`

## Files Included

### `/robot/*`
- `RobotContainer.java` (required) - Used for binding controls to functions
- `SwerveModule.java` (required) - Hooks up controls to drive chain
- `Robot.java` (required) - Place where code execution starts
- `Main.java` (required) - Define main class
- `LimelightHelpers.java` (required - dependent) - Used for functions of the limelight
- `CTREConfigs.java` (required - dependent) - The config file for CTRE
- `Constants.java` (optional) - Stores public values used in the code for easy access

### `/robot/commands/*` (Dependent on Robot)
- `TeleopSwerve.java` (required) - Controls drive chain

*Everything else depends on the robot*

### `/robot/subsystems/*` (Dependent on Robot)
- `Swerve.java` (required) - Controls drive chain & (opt) limelight calculations

## Libraries to Know

### Common Imports
- `import edu.wpi.first.wpilibj.smartdashboard.SmartDashboard;` - Displays info in a GUI
- `import edu.wpi.first.wpilibj.Joystick;` - Imports Joystick functionality
- `import edu.wpi.first.wpilibj.XboxController;` - Imports XboxController requests

### Project Imports
- `import frc.robot.commands.[File];`

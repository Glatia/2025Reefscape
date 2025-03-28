# 2025Reefscape

Team 6343's 2025 FRC robot code for Reefscape, officially known as Leviathan. Leviathan's code is written in Python and is based off of Robotpy's Commands V2 control system.

The code is divided into several packages and files, each responsible for a different aspect of the robot function. This README explains the function of each package, and some of the variable naming conventions used. Additional information about each specific class can be found in that class' Python file.

## Code Highlights
### State Subsystems
Most subsystems are children classes of [`StateSubsystem`](subsystems/__init__.py). This gives us enhanced logging capabilities and allows us to easily add additional features throughout the season via adding in additional states.

### Highly Scalable Code Structure
Our code is divided into 3 groups:
- [`Superstructure`](subsystems/superstructure.py) (comprised of all subsystems)
- [`Intake`](subsystems/intake.py) (Compliant wheel mechanism on the game piece manipulator)
- [`Drivetrain`](subsystems/swerve.py) (The swerve drivebase)

Using this system, we can use the Superstructure to handle all major subsystem states, which prevents conflicts between subsystems (such as the pivot moving inside the elevator and the elevator attempting to extend).

## File Functions

[`subsystems`](subsystems)

Contains the code for all subsystems. Each subsystem includes simulation support and data logging for match replay and analysis.
More information about the inner workings of each subsystem can be found in their respective file.

[`deploy`](deploy)

Contains all auto routines generated by PathPlanner and Choreo. Also includes all [Elastic](https://github.com/Gold872/elastic-dashboard) layouts and [AdvantageScope](https://docs.advantagescope.org/) configurations.

[`lib/elasticlib.py`](lib/elasticlib.py)

Contains all Elastic code for manipulating the driver dashboard.

[`lib/limelight.py`](lib/limelight.py)

Contains the LimelightHelpers [translated from Java](https://github.com/LimelightVision/limelightlib-wpijava/blob/89accc690a9b5bc5cfb0914ebbb444d66dd8ce3b/LimelightHelpers.java) for reading Limelight data from NetworkTables.

[`tests/pyfrc_test.py`](tests/pyfrc_test.py)

Contains test code executed before code is deployed to the robot. This ensures that no uncaught errors get deployed to the robot, which could result in a devastating match loss.

[`vision`](vision)

Contains all Limelight pipelines used by our Vision subsystem. These are manually tuned at each event in order to provide the best AprilTag visibility.

## Credits

This robot could not have been programmed without the incredible talent, skills, and determination from the following:
- Richard Amerman, Software Mentor
- Christopher Snelson, Software Mentor
- James Haddix, Software Director
- Caden Dalley, Swerve Specialist
- Chase Funk, Auto Specialist
- Matthew Murten, Elevator Specialist
- Micah Nguyen, End Effector Specialist
- Chimaraoke Okafor, Auto and Climber Specialist
- Raiden Snelson, Vision Specialist

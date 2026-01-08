# RoboRacer Rules
_Note: This is a draft of v3 rules. Commentary will be removed in the final version._

_Version: 3.2026-draft_

<!-- https://discourse.devontechnologies.com/t/css-for-markdown-numbered-headings/71404/3 -->

<style>
body {
  counter-reset: h1;
  counter-reset: p;
}
h1 {
  counter-reset: h2;
}
h1::before {
  counter-increment: h1;
  /*content: counter(h1)  ". ";*/
}
h2 {
  counter-reset: h3;
}
h2::before {
  counter-increment: h2;
  /*content: counter(h1) "." counter(h2) ". ";*/
  content: counter(h2) ". ";
}
h3::before {
  counter-increment: h3;
  /*content: counter(h1) "." counter(h2) "." counter(h3) ". ";*/
  content: counter(h2) "." counter(h3) ". ";
}
h3 {
  counter-reset: h4;
}
h4::before {
  counter-increment: h4;
  content: counter(h4, lower-alpha) ". ";
}
p::before {
 /* counter-increment: p;
  content: "§ " counter(p);
  margin-right: 1rem;
  font-weight: bold;*/
}
hr {
  counter-reset: p;
}
</style>
<!-- <style>
.post ol {
  list-style-type: lower-alpha;
}
.post ol ol,
.post ul ol {
  list-style-type: lower-roman;
}
.post ol, .post ul, .post p {
  margin-bottom: 0rem;
}
h2, h3, h4, h5, h6 {
  margin-top: 1rem;
  margin-bottom: 1rem;
}
</style> -->

## Outline
The main concept is to go though v2 rules, and filter out those that are not required anymore. In general, v3 should be ready for **all** competitions, introducing harmony and transparency to the overall competition environment.

Current idea is to provide a set of rules (also, general rules) and then, optionally, competition modifications (also, additional rules).

Even though the aim is to make the general rules shorter, it should give multiple options to host a competition; then, inside the additional rules, you specify which parts apply.

The final rules should be coherent and leave smaller window for possible mistakes, e.g., officially having an UK competition in Pennsylvania.

Note: Parts of these rules are taken over from rules of past ~16 competitions. Credits go to the people creating those rules. (Even though they are mostly unknown.)

In the rules, we should cover:

- Definitions
- Car
- Track
- Competition Area
- Practice
- Inspection
- Qualification
- Timed Race
- Head-to-Head Race

On the other hand I want to avoid:

- Duplicit rules (e.g., parts about the box on the car). <!--replace with references-->
- Rules that are not used anymore (or not used at all).
- Change will/must into may in parts where the rules might not be applied because of the competition setting (e.g., small competitions have different need than big competitions).

---

## General

<!-- Add reference to RFC for MUST, MAY, SHOULD, ... This makes defining rules a lot easier: https://datatracker.ietf.org/doc/html/rfc2119 -->

These rules apply for all official in-person RoboRacer competitions.

The rules used in a competition are posted on the competition website along with a link to the specific version in the rules repository.

With every competition instance, general rules are accompanied by competition rules.

- Competition rules MAY alter general rules or introduce additional rules.
  - In parts where both documents contradict, competition rules take preference.
- Note that competition rules MAY be versioned differently, e.g., by having a changelog.
- Organizers reserve the right to change the rules applied in the competition.
  - Subsequent changes MUST be announced to all registered teams.

<!-- _General rules SHOULD NOT change after announcing them. Competition rules MAY change even later._ -->

<!-- _Note: It is better to remove / relax something. It is NOT RECOMMENDED to add more constraints._ -->

Violating the rules MAY result into a team warning. Upon receiving three warnings, the team MAY be disqualified from the competition. Multiple disqualification and repeated misbehaviour MAY result into a ban, i.e., unability to attend future competitions.

- Note that warnings are induced on whole teams not individuals.

Ultimately, organizers reserve the right to have a final say when interpreting the rules.

- This also applies for, e.g., assigning a blame in the case of vehicle collision in Head-to-Head.

These rules are organized as follows:

- [Definitions](#definitions)
- [Vehicle specifications](#vehicle-specifications)
- [Track](#track)
- [Competition organization](#competition-organization)
- [Registration](#registration)
- [Eligibility checklist](#eligibility-checklist)
- [On-site registration](#on-site-registration)
- [Session](#session)
- [Practice](#practice)
- [Inspection](#inspection)
- [Qualification](#qualification)
- [Race](#race)
- [Time Trial](#time-trial)
- [Head-to-Head Race](#head-to-head-race)
- [Awards ceremony](#awards-ceremony)


## Definitions
<a id="definitions"></a>

- Team: A group of people with a racing car interested in a competition.
    - Registered team: Team that registered to the competition using an official registration method, e.g., sending a registration form.
    - Approved team: Registered team that sent all required materials to the organizers before the deadline and passed all necessary checks.
    - Participating team: Approved team that successfully registered on-site.
    - Inspected team: Participating team that have at least one inspected car.
    - Qualified team: Inspected team that successfully finished the Qualification.
- Team Member: A member of the team. Each person MUST belong to only one team during the competition.
    - Captain: A team member that represents the team and is used as a contact person by the competition organizers. Teams choose their captain during the on-site registration for the duration of the competition.
    - <a id="operator"></a>Operator: A team member that is holding the remote controller in order to hit the kill-switch when necessary.
- Car: Vehicle used in the competition, assembled according to the Vehicle specification. Each team MUST have their own car.
    - Inspected car: Car that successfully passed through the Inspection.
    - Hardware list: List of components that the car is composed of along with their costs. All parts of the Vehicle specification MUST be addressed along with additional sensors.
    - Kill-switch: A method to remotely and immediately stop the car.
- Track: Delimited area used for racing.
    - Track border: A barrier that delimits the driveable area.
    - Track section: Part of the track along its centerline spanning across the whole width.
    - Starting line: Line (physical or virtual) on the ground that marks the starting position of a car. MAY be identical to Finish line.
    - Finish line: Line (physical) on the ground that marks the end of the lap on the track. MAY be identical to Starting line.
- Session: Block of specific competition part.
    - Slot: Time block reserved for a subset of teams. Single session usually contains multiple slots.
    - Heat: Single instance of n-teams racing on the track. A race can be composed on multiple heats.
- <a id="touch"></a>Touching: Moving an object by less than 5 cm.
- <a id="crash"></a>Crashing: Moving an object by at least 5 cm. When interacting with another car, crashing means significantly changing its expected trajectory.
- Overtake: Act of bypassing opponent car by at least half of its length.
- Penalties: Minor punishments for not adhering to the rules.
- Violations: Major infringements of the rules.
- Warning: Issued for violating the rules. Three warnings may lead to disqualification from the competition.
- Disqualification: Revoking the ability to attend the competition.
- <a id="whistle"></a>Whistle: Sound signal to raise teams' attention. Used during the race to highlight important event. May be accompanied with flags.
- <a id="flags"></a>Flags: Visual signal to the teams. May be accompanied with whistles. When flags are used during the competition, their meaning is as follows:
    - Checkered flag: A flag is raised if the team is on the last lap. The flag is dropped and then waved when the team finishes and wins the current heat.
    - <a id="red-flag"></a>Red flag: A flag is raised if a race-stopping car crash occurs. The flag is dropped after all cars are stopped, and the team representatives are allowed to approach the track.
    - <a id="green-flag"></a>Green flag: A flag is raised to signal that the race is safe to continue for the stopped cars. The flag is dropped, and the race resumes.
    - Blue flag: A flag is raised during open testing to indicate that a team needs to let another team pass.
    - Yellow flag: A flag is raised to indicate that the teams have to drive slowly. Yellow flags MAY be also placed on the track to define a slow-speed section. <!-- This used to be "warning for a rule violation". -->
    - <a id="black-flag"></a>Black flag: A flag is raised if the team is disqualified. The flag is dropped after the disqualified team stops the car and leaves the track. The opponent is allowed to continue the race.


## Vehicle specifications
<a id="vehicle-specifications"></a>

Each vehicle will be inspected during the competition whether it meets the specified criteria. In case the criteria are not met, the vehicle is not allowed to be used in the competition.

1. Size
    - Width: 296mm ± 10%
    - Length: 568mm ± 10%
    - Height: ≤ 400mm
    - The size limit is induced on the fully equipped car, i.e., as used during the race.
        - The height limit MUST be obeyed at all times, e.g., it MUST NOT be violated because of springs.
2. Weight
    - ≤ 5kg <!-- Consider updating this. -->
    - The weight limit is induced on the fully equipped car, i.e., as used during the race.
3. Chassis
    - No additional limits.
    - Recommended: Traxxas 1:10 (e.g., TRA74054, TRA6804R, TRA68086)
3. Bumpers
    - Front bumper (at least 5 cm thickness) from a soft material is required.
    - The bumper must be attached to the car in a way that it does not fall off at any time.
    - Example: TRA7436 + TRA7437 + TRA7415X
4. Tires
    - No limits.
4. Drivetrain
    - No limits. Both 2WD and 4WD are allowed.
4. Motor
    - Electric motors only.
    - Only a single motor can be used for operating the drivetrain.
    - Torque: 0.237N·m (100A @ 3500RPM/V) ± 10% <!-- Used https://things-in-motion.blogspot.com/2018/12/how-to-estimate-torque-of-bldc-pmsm.html -->
    - Recommended: Velineon 3500
5. Battery
    - Up to **4S** for powering the motor.
    - Additional batteries for powering other components are not limited.
5. Electronic Speed Controllers
    - No limits.
    - Recommended: VESC
5. Remote controller
    - No limits.
    - It must have a kill-switch ability so the [Operator](#operator) is able to stop the car immediately and remotely.
6. Compute
    - No limits, but all computation during the race MUST be done onboard the vehicle.
    - Recommended: NVIDIA Jetson Xavier, NVIDIA Jetson Orin, Intel NUC, etc.
7. LiDAR
    - Number of planes: Not limited
    - Detection range: Not limited
    - Scanning frequency: ≤ 40Hz
    - Angular resolution: ≥ 0.125°
    - Recommended: Hokuyo UST-30LX, Hokuyo UST-10LX, etc.
8. Camera
    - No limits. Monocameras and stereocameras are allowed.
9. External localization
    - GPS and similar indoor solutions are not allowed.
    - Exception: Organizers MAY used them.
10. Production cost
    - No limits.
    - **Starting from 2027 it will be limited to ~ 5000$.** (Current estimate.)
    - Contains the price of all components + price estimation of custom parts.
        - The retail price must be free of any discounts.
        - Custom parts: The price estimate for a company to manufacture your source file.

Other sensors are not restricted, however they MUST be mentioned in the hardware list.


### Vehicle parameters

- You MUST NOT hinder the opponents from detecting your car, e.g., using materials/colors to adjust the car reflectivity.
- At all times, the car MUST occupy a square-shaped space of size at least 12×12 cm at every horizontal plane between 10 to 30 cm above the ground. Usually, this is achieved by placing a 12x12x20cm box on top of the car at its back.
    - The box should be made of LiDAR perceivable material (e.g., cardboard).
    - As long as the object results in the desired LiDAR signature, the object can have any additional aerodynamic shapes added like fins, wings, etc.
    - The box may be of any color as long as it is easily perceivable by the LiDARs of the other cars.
- Tire modifications that may leave residuals on the track surface are not allowed.
    - Forbidden modifications are, e.g., cleaning using soaps, or sanding the tires.
    - Volatile chemicals (e.g., alcohol-based cleaning liquids) are allowed.

## Track
<a id="track"></a>

Racing track is a delimited area used for racing.

The competition rules MUST specify:

- Nature of the surface (flatness, reflectiveness, material).
- Nature of the room (e.g., walls/windows, ceiling type).
- Type of delimiters (e.g., air ducts, cardboard boxes).
- Height of delimiters.
- Maximum size (e.g., area) of the track.
- List of used track features.


### General track notes

- The surface friction MAY naturally slightly differ across the track.
- When the room is surrounded by windows or semi-transparent surfaces, it might result into incorrect sensor measurements.
- When the track is delimited by a set of pipes (on top of each other) there might be gaps between them.
- Due to the car tilting, the sensors might see over the track borders or see the floor.
- When multiple tracks are present, their parameters, features and overall nature may differ.
    - Current session may differ as well. In that case the organizers MUST clearly state the current session on each track.


### Track behaviour

- The teams are obliged to be respectful with other users of the track.
    - Teams are encouraged to pay attention when moving around the track, especially more when, e.g., running or jumping.
    - Teams are not allowed to obstruct other teams by any means (e.g., if specified, leaving a stationary car on the track outside of the designated area).
    - Teams are not allowed to endanger other teams, cars and especially spectators and by-goers by an inappropriate behaviour.
- The teams should not intentionally run code that they expect will crash into the track boundaries. Overly aggressive testing may mess with the track layout.
- While testing the car, the team should limit the amount of damage to the track to an absolute minimum.
- Whenever using the track, there has to be at least one team member ([Operator](#operator)) that keeps an eye on the car and is prepared to activate the kill-switch.
- Teams that are not taking part in the session should avoid the track at all times.


### Track features

A list of possible track features follow. Competition rules will specify, which of them (might) apply.


#### Dead-ends

Track contains parts that do not lead to the finish line.

- Driving into these track sections is not penalized.


#### Speed-restricted sections

Track contains sections with defined speed limits.

- Driving with forbidden speed is considered as a ... _(which type of violation?)_ <!-- TODO -->
    - During the race, the team has to stop the car and move it before the speed-restricted section.
- The speed limit is defined in one of the following ways:
    - Area delimitation with special markings.
- The competition rules have to specify:
    - Speed limits used within the competition.


#### Pit lane

Track contains sections that are marked as a pit lane.

- When this track feature is used, deliberate stopping outside the pit lane is not allowed.
    - Stopping outside of pit lane is considered as a ... _(which type of violation?)_ <!-- TODO -->
- Teams are allowed to add cars to the track only at a pit lane area.
    - Teams are highly encouraged to do the car removal here as well, unless required by the current situation.


#### Open walls

Track borders are not closed, i.e., there are horizontal gaps in them.

- Gaps might be in the inner walls as well as in the outside walls.

- Inside the gaps the track border is delimited by a tape on the ground (or any other marking technique).

- Driving inside the gaps is not allowed.
    - Crossing the track border is considered as a [touch](#touch).
    - Crossing the track border by parts of at least 3 wheels is considered as a [crash](#crash).


#### Intersections

_Note: This won't be used for ICRA race._

<!-- The track contains intersections, i.e., a track section where multiple driving directions are allowed.

- In the intersection area, following rules MAY apply:

    - Speed limit
    - Right of way
    - ...

- The lap is marked as completed only when all track sections were driven through during it. -->


#### Surface changes

The track surface is deliberately altered in certain track sections.

- This change can both reduce or increase the surface friction.
- On the edge of the surface change, the track does not have to be entirely flat; a small height change may occur.
    - This change is below a certain threshold to not pose a threat to the cars.
- Competition rules must specify:
    - How the surface is altered.
        - The surface cannot be altered by methods that could damage the cars, e.g., spilling water on the track.
    - Maximum height change between two surfaces (mm).


#### Track splits

The track contains track splits, i.e., the track section is split into multiple paths.

- Driving through the track may be performed by any of the paths. They are considered equal.
    - However, they might not be equal performance-wise, e.g., taking one of the paths might be more beneficial than the other.
- Driving though only one of the paths is required for lap completion.
- Competition rules have to specify:
    - Track width in the split section, in case it would differ from the general track width limit.


#### Slopes

The track contains a sloped section, e.g., a bridge.

- In this section the track is generally not flat.
- Competition rules must specify:
    - Maximum elevation (%).

_Note: When using this track feature it can't prevent teams using single plane lidar from completing a lap._


#### Banks

The track contains banks, i.e., the track is elevated in the outer parts of turns.

- The track is not flat in this section.
- Competition rules must specify:
    - Track width that is not banked next to the bank [m].
    - Minimum bank width [m].
    - Maximum bank elevation [%].


## Competition organization
<a id="competition-organization"></a>

The competition is composed of:

- Registration
- On-site registration
- Practice
- Inspection
- Qualification
- Time Trial
- Head-to-Head Race
- Awards ceremony


## Registration
<a id="registration"></a>

- Team interested in participating in the competition has to register using a official registration method. This method may have its deadline.
- Registrations received after the deadline may not be accepted.
- Registration is confirmed by the competition organizers after completing all required steps. These are, but not limited to:
    - Filling up the registration form.
    - Submitting a video of your car driving autonomously.
    - Submitting a hardware list.
        - Hardware list will be made publicly available for other teams after the competition.
- Not submitting in time may void the registration.
- Registration not confirmed by the organizers is not deemed valid.


## Eligibility checklist
<a id="eligibility-checklist"></a>

The team is eligible to attend the competition as long as:

- Registration fee is paid.
- Registration is confirmed by the organizers, i.e., the team is approved.
- All required forms and materials are sent to the organizers by the given deadline.
    - The car does not differ from the submitted hardware list.


## On-site registration
<a id="on-site-registration"></a>

Upon their arrival to the competition site, the teams MUST promptly register on-site in order to race.

- The teams MUST register on-site in the given time frame.
    - Exceptions are allowed as long as they are discussed with the organization team.
    - If a team is late for the registration, it MUST inform the organizers (e.g., for flights with a tight deadline, they can send the flight number to the organizers and this is considered enough notice).

- The on-site registration is composed of:

    - Confirmation of team details.
    - Pre-registration of the car used within the competition. This also includes associating the car with its hardware list.
        - Organizers MAY allow cars without the hardware list if they can approve all required components on the spot.

- Upon completing the on-site registration the team is allowed to:

    - Attend the competition.
    - Make use of the team designated area.
    - Sign in to the sessions.

- Not completing the on-site registration in time MAY result into a team disqualification from the competition.


## Session
<a id="session"></a>

Parts of the competitions are organized in so-called sessions.

- The organizers will use following various notification systems during the sessions, such as (but not limited to). Competition rules specify which apply:
    - [Colored flags](#flags).
    - [Whistles](#whistle).

- The session/slot/heat timers are fixed to the time slot and no extensions are given.
    - Missing out a time slot does not give the team an additional slot.
    - Upon their mutual agreement, the teams are allowed to exchange the slots by informing the responsible organizers.

- Opt-in session slots are designated on a first-come-first-serve (FCFS) basis.
    - The teams register individually for a given time slot using a method announced by the organizers during on-site registration.
        - There MAY be a limit of time slots each team can register into.
    - These slots are contained in, but not limited to:
        - Closed Practice
        - Inspection
        - Qualification
        - Time Trial

- Organizers MUST share timetables of other session slots early enough so the teams have time to prepare.


## Practice
<a id="practice"></a>

Practice is a session for the teams to train and test their car directly on the track.

- Practice track SHOULD contain all track features used during the competition, but its layout may differ.
    - When the layout differs, there MUST be another practice session before the actual race to allow the teams to map the track.


### Practice variants

A list of possible practice variants follows. Competition rules specify which of them apply.


#### Shared Practice (Group)

Practice session where the track is opened for a subset of teams specified by the organizers.


#### Open Practice

Practice session where the track is opened for all teams.


#### Closed Practice (Single)

Practice session where the track is reserved for one team only.


#### Mapping Practice

Practice session used for mapping the track. It MAY be organized as any other practice variant with additional rules:

- Teams are not allowed to test their racing algorithms during this practice.
- A speed limit MAY be employed for this practice, especially when it is Shared.
  - Not adhering to the speed limit MAY result in a warning.


## Inspection
<a id="inspection"></a>

The purpose of the Inspection is to check that the hardware of the cars meets the competition requirements and the cars are not dangerous for the environment, opponents, and people.

- The inspection of the vehicles is done in a dedicated time-frame.
- The inspection is done by the race referees.
- The inspection MUST be completed before the Qualification.
    - Any significant changes to the cars hardware MAY void the inspection.
    - Teams are advised to inform the organizers prior to these changes.
- When a hardware list is submitted as a part of the registration, the car is checked to match these parameters.
    - Organizers MAY also approve using cars that do not match their parameters.
- Car that is not inspected is not allowed to be used in the competition.


## Qualification
<a id="qualification"></a>

Qualification is a session testing the autonomous capabilities of the racing car. The goal is to complete a single lap without touching and crashing anything, such as, track borders, obstacles, or other cars.

- Qualification is done with a single racing car on the track.
    - Other cars may be used as static/dynamic obstacles.
- Only inspected car can be used in the Qualification. <!-- In case the team intends to use multiple cars during the competition, they have to qualify with all of them. -->
- The car MAY be qualified during a practice session.
- The Qualification MAY be merged with Time Trial.
    - In this case the obstacle avoidance capability has to be checked separately during a dedicated session, e.g., during Practice.
- There are no penalties. Touching and/or crashing results into another try. (Up to the time limit.)
    - Teams MAY manually place the car to the starting line.
- Organizers MAY add more slots based on the success rate of the teams.


## Race
<a id="race"></a>

Main part of the competition is composed of race sessions in which the teams are scored.

- Teams MUST pass the Qualification to join the races.

- The race starts in one of the following ways. Competition rules specify which are used.
    - **Manual**: Upon signalizing, the teams start their cars manually.
        - The signal can be one of many types, e.g., visual, audial.
    - **Automatic**: Starting signal is transmitted directly into the car.
        - The signal denoted as "Go" is sent to start the race.
    - **Mixed**: Each competing team may select its starting method.
        - Organizers SHOULD ensure that both signals are sent in such a way that there is no advantage of using one over the other.

- The race start has one guaranteed signal: "Go". Competition rules may add other signals.
    - _Note: Use this as a "template" for automatic start up. Then merge it._
    - Usage of other signals (such as "Ready" and "Set") much be specified in the competition rules.
    - Countdowns between the signals may differ for every start.

- The race is stopped (paused) by, e.g.:
    - Raising a [red flag](#red-flag).
    - Raising a [black flag](#black-flag).
    - Using a [whistle](#whistle).

- During the race, the [Operator](#operator) has to hold the remote in a raised hand to be clear that the car is not manually controlled (so-called _Operator/Driver stance_).

- Obstacles and opponents may be overtaken from both the right or the left side.


### Race penalties

During a race certain mild accidents may happen. Following steps and penalties are applied.

- Touching is not penalized.
    - Excessive/repeated touching MAY be considered as a crash.

- Upon crashing into an obstacle/track border, the team has to:
    1. Stop its car.
    2. Move the car (by hand or using the remote control) to the side of the track next to the latest position before crash.
    3. Repair the track and/or place the obstacles to their appropriate positions.
    4. Wait for the clearance from the organizers (using, e.g. [a green flag](#green-flag)).
    5. Start the car and continue the race.

    - During all of this, the opponent’s car must not be restricted by the team’s actions and the opponent is allowed to further race without stopping its car.

- Upon crashing into the opponent (e.g., one of the cars significantly diverges from its expected trajectory):
    1. Referees call the crash and pause the race; the teams have to stop their cars.
    2. Referees judge which car is at fault.
    3. Both cars are placed at the location of the crash, with the at-fault car placed behind the other car by 2 meters (direct distance between the cars).
        - If the team that was crashed into is able to autonomously detect and recover from the crash by stopping on the side of the track, that team is granted an extra head-start of 1 meter before resuming the race (i.e., the at-fault car is placed 3 meters behind the other car).
    4. The referees resumes the race.


### Race violations

Violations are major rule infringements that MAY result into warnings. Severe offenses MAY even lead to disqualification from the competition.

- A crash is not considered a warning unless judged by the referees.
    - Crashes that result in a warning include but are not limited to "malicious" crashes where the autonomous car did not attempt to slow down or steer away from the opponent.
    - Under special circumstances, the referees may decide to give a warning to a team with the option of stopping the race to address the issue. The team has a maximum of 5 minutes to fix the issue and resume the race.
        - This does not apply for double-elimination.

- The algorithms MUST NOT intentionally hinder the opponent or perform any damage to it. Specifically, maneuvers such as deliberate crowding of a car beyond the edge of the track or any other abnormal change of direction are strictly prohibited.
    - Violating this rule MAY lead to disqualification regardless the amount of warnings issued.

- Teams are allowed to report other teams' violations.
    - If the reported team is found guilty, it receives a warning; otherwise it goes to the reporting team.

- Upon receiving 3 warnings, the team is disqualified from the competition.
    - During a race this automatically means the opponent wins.


## Time Trial
<a id="time-trial"></a>

<!-- _Note: Competition rules should specify: #heats, time per heat; e.g. 2x5 minutes._ -->

Time Trial is a race with a goal to drive through the designated track as fast as possible and as consistently as possible. The idea is to push the algorithms to their limits.

- Each team MUST pass the Qualification to be able to participate in the Time Trial.

- Time Trial is used as a seeding technique for the Head-to-Head Race.
    - This does not apply if Head-to-Head does not require seeding.

- The race consists of multiple heats, two by default. Each heat lasts for a given time (e.g., 5 minutes), and the goal is to drive a single lap in as short time as possible and to drive as many complete laps as possible. Crashing and stopping the car does not pause the heat timer.

- The teams are allowed to change the configuration of their algorithms in between the heats, and even during the heat. When the configuration is being changed during the heat, the car MUST stand still. In other words, the teams cannot update the configuration on-line while the car moves.

- The map (track layout) is known a priori (from a practice before) and the track layout does not change during the race. Keep in mind that cars crash into the walls and the layout of the track might slightly shift over time. Please consider this in your algorithms.


### Evaluation

- Each team will be evaluated based on the following criteria:

    - Lap time.
        - Lap time is measured between two subsequent finish line crossings.
        - It will be measured with a time-keeping system provided by the organizers.
    - Consecutive uninterrupted laps.
        - A (1) uninterrupted lap is counted if and only if in-between the last two finish line crossings the car was not stopped. <!-- Consider whether to also count deliberate stopping when changing the configuration. -->

- Evaluation is performed in multiple categories, each one resulting in its result table.

    - Fastest laptimes: Teams are ranked based on their fastest lap times.
    - Consecutive uninterrupted laps: Teams are ranked based on the highest number of consecutive uninterrupted laps they complete.

- Points are awarded in each category separately according to the ranking of the teams.

    - A (1) Point is given for every team that has worse scoring.

- The final score for the Time Trial is the sum of the points from all categories.

    - Note that the best achieved results may be from different time slots.
    - This allows teams to push their algorithms to the limits in each of the categories.

- Should a tie occur in the final ranking, the team with more consecutive uninterrupted laps is ranked higher.
    - Additional tie is resolved by fastest lap time.
    - In case the teams tie with both criteria, the tie is, with respect to the seeding, resolved by a random method (e.g., coin flip).


## Head-to-Head Race
<a id="head-to-head-race"></a>

<!-- _Competition rules have to specify: Timeslot, competition type, ..._ -->

<!-- _Outline: What?, General overview, starting position, race start, race rules, penalities, etc._ -->

Head-to-Head race is a race with multiple cars on the track at the same time. The idea is to drive as fast as possible while not crashing into the track and/or opponent.

- During one Head-to-Head race two teams race against each other.

- The initial placement of the competing cars in one of the following ways. Competition rules specify which are used.
    - **Side-by-Side**: Both competing cars start on the same starting line.
        - The teams will start side-by-side approximately 30cm apart.
    - **Staggered Grid**: Competing cars start in a staggered grid.
        - First starting position is placed in front of the starting line, closer to the side that should be more beneficial.
        - Second starting position is placed 30cm to the other side, 80cm behind.
        - In case more cars are present, their placing follow the "zig-zag" pattern.

- In the first heat, the team that ranked higher in Time Trial chooses the starting position. In case of more heats:
    - In the second heat, the teams switch sides.
    - Should a third heat be necessary, a coin flip will determine the starting position. The team that ranked higher in Time Trial will call the coin flip (i.e., heads or tails). The team that wins the coin flip chooses the starting position.

- As opposed to Time Trial, no reconfiguration is allowed during the race.


### Tournament types

Below a list of possible tournament types follows. Competition rules specify, which are used.

#### All-vs-all

Every team races with every other team.

- The final ranking is determined by the amount of wins.

<!-- _Note: This won't be probably ever used for a competition, but mostly for a small scale events._ -->

<!-- _Another note: It is slightly better to do every race twice._ -->

#### Single Elimination

The tournament is organized as a Single Elimination in a series of rounds.

- The bracket is seeded using the results of Time Trial.
  - Bracket should be designed properly, e.g., it should ensure balancing in the teams racing against each other.

- Each race consists of up to three heats.
  - Team that loses the race is eliminated from the tournament.

#### Double Elimination

The tournament is organized as a Double Elimination in a series of rounds.

- There are two brackets, winners' and losers'.
- The winners' bracket is seeded using the results of Time Trial.
  - Similarly to Single Elimination, the bracket should be designed properly, e.g., it should ensure balancing in the teams racing against each other.
- Each race consists of a single heat.
  - Team that loses a race for its first time is moved to the losers' bracket.
    - Team that loses in the losers' bracket is eliminated from the tournament.
  - In case that a team loses for its first time in the Final Round, an additional heat is provided.


### Competition model

Below a list of possible competition models follows. Competition rules specify which are used.

#### Single Cup

All teams are racing in the same cup.


#### Single Cup + Final Four

All teams are racing in the same cup using Double Elimination, but the finals (with the top four teams) are performed using Single Elimination.


#### Double Cup (Classic Cup, Master Cup)

During the seeding, the participants are split into two groups, cups. Note that the rules may differ between the cups. In that case the Competition rules specify how.

Admission to Master Cup (with respect to the seeding) is done as follows:

- Master Cup may contain up to the half of the team roster.
- First 4 teams automatically proceed.
- Up to the first half, all teams have an opportunity to either join or not.
- The organizers MAY allow to fill the rest of the Master Cup by teams that placed top 3 in the last 3 years (1100 days).

If the racing track is changed for the Master Cup, the teams are given an extra practice session to test their car and algorithms on the new track.


### Evaluation

- Each team will be evaluated based on the following criteria:

    - Amount of laps completed.

- The first car that completes given amount of laps wins.
    - In case that this objective is not achieved by any car, the amount of completed laps along with the achieved progress on the track is the decisive factor.

<!-- Consider listing other tiebreaker factors, e.g., overtakes, crashes. -->


## Awards ceremony
<a id="awards-ceremony"></a>

The competition concludes with the Awards ceremony. The ceremony may be accompanied by a workshop session.

- During the workshop session, top 4 teams from each cup are obliged to briefly talk about their approach.
    - In case a team cannot attend the workshop, they may send a short video presentation instead.
    - The presentations are shared after the competition on the competition website.

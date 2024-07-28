# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).
This changelog starts at version 0.2.0.

## 0.12.2 - 2024-07-28

### Updated

  - Updated Elixir version to 1.14 and Erlang to 25.3.

## 0.12.1 - 2022-07-22

### Added

- New role: "Pictomancer".
- New role: "Viper".

## 0.12.0 - 2022-09-03

## Added

- Teams now have a separate permission level, above what was previously called admin, that
  basically inherits all of the stuff the team creator could do, with exception of deleting
  the team, which can still only be done by the team creator.
- Likewise, what was previously called "team admin" is now called "team organizer", as the
  NEW "team admin" permission level supersedes it.
- Added an explainer (visible only to team admins and the creatore) that explains all this.

## Fixed

- Guarded a few more server routes against unauthorized access.

## 0.11.5 - 2022-08-29

## Fixed

- Fixed Dragoon being unavailable in role selection.

## 0.11.4 - 2022-08-24

## Fixed

- Non-role-only role selection now correctly shows all roles.

## 0.11.3 - 2022-08-22

## Added

- The dashboard now shows who is organizing each event.
- Added a cool eorzean font for the logo type.

## Fixed

- There's now a confirmation popup before deleting an attendee.
- The "Log in with Discord" button is now hidden when just having logged in with
  Discord.

## 0.11.2 - 2022-08-05

## Fixed

- Select fields that are set to required now perform a (client-side) check, so that
  people can't submit incomplete forms.

## 0.11.1 - 2022-07-04

## Fixed

- The mobile manage page now renders empty parties correctly.
- Some cold code paths that had invalid accesses have been fixed.

## 0.11.0 - 2022-06-30

## Added

- The manage attendees page now displays a read-only, limited display of
  information when viewed on mobile.

## Changed

- Instead of using custom components, single and multi select custom fields
  now use native HTML elements.

## Fixed

- Fixed a preload issue causing team admins to be unable to create events in
  that team.

## 0.10.6 - 2022-06-17

## Fixed

- Fixed a regression where team members could faux-assign attendees to parties.
- Team admins can now create event templates. Apparently, this was always supposed
  to work, but I messed up checking for the permissions.

## 0.10.5 - 2022-06-10

## Fixed

- Party export now works when you have one or more parties without anyone in it.
- Empty attention list reasons aren't displayed as "null" anymore.

## 0.10.4 - 2022-05-27

## Fixed

- Reintroduced the full row drag, and only the Discord text can be selected for now.

## 0.10.3 - 2022-05-16

## Added

- Text in cells can now be selected.
- Custom field text is now displayed in a tooltip when hovered over, in case
  the text is very long.

## Changed

- Shield healers now display in a darker shade of green compared to regen healers.
- The party display starts with displaying roles by default.
- The selection modifiers have been moved into a new popover to conserve space.
- Dragging now works via a drag handle from the very left of the table
  (until AG-Grid has fixed their bug of dragging not being able to be
  conditionally turned off.)

## 0.10.2 - 2022-04-22

## Fixed

- Fixed the party display view sorting, again(?)
- Some big internal rewrites.

## Changed

- Changes some links to documents and sources around.

## 0.10.1 - 2022-04-13

## Fixed

- Fixed the party display view sorting.

## 0.10.0 - 2022-04-07

## Added

- Roles can now be trimmed down to select one class type, e.g. tanks only.
- Added more help text around the IGN input field.

## Fixed

- Added more fallbacks if the Discord ID can't be extracted.

## 0.9.1 - 2022-03-17

## Fixed

- Don't show edit/delete buttons when you don't have permission.
- Refine the conditions to show an empty party display.

## 0.9.0 - 2022-03-15

## Added

- Replaced the old attendees page with the new one.
- You can now display parties in the new attendees table.
- Added buttons to delete and edit attendee data, like in the old table.
- Added a section to unhide hidden columns.
- Added a quickstart tutorial the first time you visit the attendees page.

## Changed

- Sort DPS roles by Melee > Phys. Ranged > Magic Ranged.

## Fixed

- Show a "no rows" overlay when there's no attendees.
- Fixed a bunch of oversights when having other blocks disabled.
- Checkboxes in the "edit event" page should now behave correctly.

## Removed

- Removed most code relating to the old attendee page.
- Removed the "show parties" attribute of custom fields.

## 0.8.4 - 2022-03-14

## Fixed

- Parties now display without anyone in them.
- Reassigning does not remove leader status anymore.
- The grid keeps its position when data changes, and doesn't jump to the top anymore
  (apparently, this was an intended behavior?? Okay???)
- Fixed worry and favor list items not showing correctly.
- Set correct permissions for the new attendees page.

## 0.8.3 - 2022-03-08

## Fixed

- Rely on a fallback discord ID in case it doesn't get collected for some reason.

## 0.8.2 - 2022-03-07

## Fixed

- Both attendee pages - new and old - don't crash anymore.

## 0.8.1 - 2022-03-07

## Changed

- Discord login now also stores the user's ID, in order to automate things further down the line.
- The disclaimer regarding what data we collect via the Discord login has been extended.

## 0.8.0 - 2022-03-06

## Added

- There is a new page for managing attendees, designed to replace the old one. This page uses
  a fully client-side data grid implementation, and supports the previous functionality, plus:
  - Column ordering/sizing/hiding/pinning preferences are saved per event in the user's browser.
  - Columns can be pinned to the left side to make it easier to gain an overview. This is on by
    default for the IGN column.
  - All columns can be filtered by a search string with fuzzy matching.
- This page also supports the party display.
  - Attendees can be assigned to parties by dragging them into the party area.
  - Titles are now shown as little color-coded badges.
- In this release, this functionality is locked behind the `/manage/attendees_new` URL.

## Removed

- Party size limits have been removed. They were stupid and arbitrary.

## 0.7.2 - 2022-02-02

## Fixed

- The templates page now loads correctly.

## 0.7.1 - 2022-01-31

## Fixed

- Fixed an inconsistency with authorizing team-external organizers.

## 0.7.0 - 2022-01-23

## Added

- You can now delete events entirely once you've cancelled them.
- You can also delete event templates now.
- Custom fields can now be set to be required for the user to fill out.

## Fixed

- The prompt to close registrations doesn't show on cancelled events.

## Removed

- Removed the role filter functionality, as it's better served by existing search and sort features.

## 0.6.0 - 2022-01-20

## Added

- Team organizer IGNs now show up blue when someone with the same IGN signs up.
- Past events now show up on the team page.
- Organizers can now edit their attendee's information.

## Changed

- Added "‘" (left single quotation mark) to the allowed characters in IGNs.
- The user "display name" field is now an IGN field.
- Select/Delete buttons in the attendee table now display in the
  front of a row, because rows can get very long, and scrolling down
  to hit a button is annoying.

## Fixed

- Party lead and selection information is now shown in the party view, even for people
  who are not organizers and only have view access.
- Past events on your dashboard are now shown newest-first, and with
  the event date displayed.

## 0.5.4 - 2022-01-05

## Fixed

- Fixed an internal server error when removing party assignments.
- Made sure team organizers are properly loaded when submitting an invalid form.

## 0.5.3 - 2022-01-05

## Fixed

- Allowed "-" in IGNs.

## 0.5.2 - 2022-01-02

## Fixed

- Events without a team's signups now work again.
- Custom field content now shows up correctly after the signup
  form has been incorrectly submitted (for example, due to an
  invalid IGN).

## 0.5.1 - 2022-01-01

## Fixed

- The prompt to add new entries to attention lists now shows only for team admins.

## 0.5.0 - 2022-01-01

## Added

- Added attention lists, which are essentially a way of keeping track
  of certain players (via IGNs). There exist three different lists
  right now, the favor list, the worry list, and the black list.
  Every team member can see the lists, but only team admins can add or
  remove entries.
- IGNs on the favor list are highlighted in green.
- IGNs on the worry list are highlighted in red.
- IGNs on the black list are unable to sign up to any events
  organized under the team.

## 0.4.0 - 2021-12-29

## Added

- Added a link to this changelog in the page footer.
- You can now collapse attendee table columns. These preferences are saved in your browser's
  local storage, unique per event.
- You can now export your party composition to a .xlsx file.

## Fixed

- Leader information now displays in the party column.

## 0.3.5 - 2021-12-28

## Changed

- Re-enabled adding co-organizers for team events.

## Fixed

- Teams with event templates now delete correctly.
- Co-organizers' usernames now correctly show on the signup page.

## 0.3.4 - 2021-12-18

## Changed

- Resized role and class images.
- You now have to click an extra button before logging in. This is to prevent anti-spyware
  functionality of certain email providers to invalidate your login link before you even get
  a chance to click on it.

## Fixed

- "’" (Right Single Quotation Mark) is now allowed in In-Game Names (because that's what some people have
  on their keyboards instead of the normal apostrophe).

## 0.3.3 - 2021-12-17

## Changed

- The relative time will now display a more precise time when the date is less than 48 hours away.
  Previously, it would display "tomorrow", even when the date was more than 24 hours away, now it
  displays "in 38 hours", for example.

## Fixed

- Team can be viewed as a not logged in user now, as it should be.

## 0.3.2 - 2021-12-15

### Changed

- XLSX exports now properly attach the registration time.

## 0.3.1 - 2021-12-15

### Fixed

- Events with name correctly export to XLSX without crashing.

## 0.3.0 - 2021-12-15

### Added

- Added a button to export attendee data to an XLSX file, for use in other Excel-format-compatible
  tools, like Google Sheets.

## 0.2.2 - 2021-12-2

### Added

- Added the "Reassign role:" header to the hover popup on the parties
  page when the roles only option is enabled.

### Removed

- Removed the option to toggle Endwalker roles.
- Removed the shortcut to quickly add EA parties. This is obsoleted by
  event templates.

## 0.2.1 - 2021-11-29

### Added

- A note showing what team an event is organized under now shows up on the signup page.

### Changed

- The team page will now show all events, even unlisted ones, for team members. The
  unlisted status will also be indicated on the dashboard.

## Fixed

- Updating a team now doesn't error.

## 0.2.0 - 2021-11-27

### Added

- Teams have been added. They can be used to organize recurring events with the same people.
- New team members can be invited via email by the team's creator.
- Newly created custom fields now differentiate between an internal name and a form field title. This
  results in the attendee table and the parties view not being endlessly stretched out, like it did
  before if you had long names (e.g. questions) as custom field names.
- Team members can either be a member (meaning they get view access to all events in the team, excluding
  the ones they created, to which they have full access), or admins (which get full access minus event
  cancellation to all events in the team).
- You can now choose to not collect attendee's names.
- Events can now be saved as templates. These templates are associated
  with a team, and can only be created by team creators or admins.
- New events can be created using a template's data.

### Changed

- When creating an event, you can now choose to associate it with one of the user's teams.
- Events are now "unlisted" by default. If it's associated with a team, it can be set to
  public so that it shows up on the team's public page.
- Actions that have to do with changing the state of the event have been moved to the bottom
  of the event management page.
- If the event is associated with a team, the is shown instead of the overview which organizers
  are involved in the event.
- Events are now displayed in a more visually appealing way on your dashboard. Events displayed there
  now also include events from teams you're a member of.

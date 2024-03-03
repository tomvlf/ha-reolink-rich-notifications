# Reolink Rich Notifications for Home Assistant

This blueprint can be used to send notifications to your mobile device when your Reolink camera
detects activity.

Multiple mobile phones are supported. Only Android is currently supported, but iOS could be added
fairly easily. I don't have a way to test it, so if you are interested in implementing it, please
send a pull request.

The [Reolink Home Assistant integration](https://www.home-assistant.io/integrations/reolink/) is
required.

The list of sensors (e.g. Motion, Vehicle, Person, Animal) that should trigger an alert can be
configured. The camera of the device the sensor belongs to is automatically determined for taking
a snapshot when an alert is triggered.

If you tap on a notification, the Reolink app is opened.

When a sensor is triggered, the automation first sends a notification with no image. Then it takes
a snapshot and updates the notification with the image. This makes it so notifications are much
faster if there's a delay in your phone receiving the image, particularly useful on slow
connections.

To avoid redundant notifications (e.g. receiving Motion + Person at the same time) there is a
configuration setting to skip notifications if the same camera has already triggered a notification
within a short time period (20 seconds by default).

Snapshots are saved in the `/media/reolink_rich_notifications/` directory of home assistant.

- Originally forked from https://gist.github.com/McDAlexander/56eb3f2e421e283460b3d641fd002ea8

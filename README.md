# Trial Flyer Generator

This repository serves as a simple web app that allows Coding Mind personnel to generate flyers for trial classes just by entering a simple URL into their web browser.

### Parameters

| Parameter Name | Description                                                                                                                                                             |
|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `name`         | The first and last name of the student.                                                                                                                                 |
| `course`       | The name of the course the trial class is for.                                                                                                                          |
| `instructor`   | The first and last name of the instructor.                                                                                                                              |
| `datetime`     | The date and time that the trial class is set to take place at. This is in the format YYYY年MM月DD日. The English flyer will present the date in the format MM/DD/YYYY. |
| `mode`         | Either the Zoom URL, or one of the following names exactly: Irvine, Seattle, Arcadia, Diamond Bar, WL, San Diego                                                        |
| `org`          | One of the following names exactly: Irvine, Seattle, Arcadia, Diamond Bar, WL, San Diego                                                                                |

To enter these parameters, replace each part of the following URL with their appropriate value and enter it into your address bar.

**Note** that you should remove the curley brackets `{ }`.

```
https://cm-edu-tech.github.io/trial_flyer/index.html?name={NAME}&course={COURSE}&instructor={INSTRUCTOR NAME}&datetime={DATE}&mode={ZOOM LINK OR CAMPUS CODE}&org={CAMPUS CODE}
```

Examples：

1. Zoom

```
https://cm-edu-tech.github.io/trial_flyer/index.html?name=John Smith&course=Roblox 1&instructor=Kevin Gee&datetime=2024年12月12日&mode=https://zoom.ui/j/123456789&org=Irvine
```

2. In Person

```
https://cm-edu-tech.github.io/trial_flyer/index.html?name=John Smith&course=Roblox 1&instructor=Kevin Gee&datetime=2024年12月12日&mode=Irvine&org=Irvine
```


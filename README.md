# Course Flyer Generator

This repository serves as a simple web app that allows Coding Mind personnel to generate flyers for courses just by entering a simple URL into their web browser and modifying a JSON.

## Quick Listing Test Page


https://cm-edu-tech.github.io/course_flyer/listing.html


## Grabbing a Course Flyer

Before starting, check if the JSON information for that course exists in the repository under `static/courses`. If it doesn't, refer to **Adding a Course Flyer**.

First, note the following parameters.

| Parameter Name | Description                                                                              |
|----------------|------------------------------------------------------------------------------------------|
| `courseId`     | The name of the JSON file corresponding to this course. For example, `"mindstorms_1"`.   |
| `campus`       | One of the following names exactly: `"irvine"`, `"seattle"`, `"arcadia"`, `"diamond_bar"`|
| `lang`         | `en` for English or `cn` for Chinese.                                                    |

To enter these parameters, replace each part of the following URL with their appropriate value and enter it into your address bar.

**Note** that you should remove the curley brackets `{ }`.

```
https://cm-edu-tech.github.io/course_flyer/index.html?courseId={COURSE ID}&campus={CAMPUS}&lang={LANGUAGE}
```

For example, for Mindstorms 1 taught in Irvine:

```
https://cm-edu-tech.github.io/course_flyer/index.html?courseId=mindstorms_1&campus=irvine&lang=en
```

If the page does not load correctly (odd text formatting or a white background), then one of the following either occured:

1. You entered the one of the parameters incorrectly.
2. You didn't add the JSON for that course yet.
3. The info on the JSON for that course is not correct (for example, the page formatting will be off if the level for the course specified is not "l1" to "l6")

The page is split into 2 parts:

- Page 1: The Main Flyer
- Page 2: A Lesson Plan/Table of Contents

You can download either by clicking on the download buttons up at the top, which will download them into a readable format. It will **NOT** look like how it appears in the browser, which is quite stretched out.

## Adding a Course

To add a course, add a JSON to the `static/courses` folder. The name of the JSON should be an ID of the course, for example `mindstorms_1.json`.

The info required is as follows:

| Parameter Name                 | Description                                                                                                                                                                                                                                                |
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `course_level`                 | `"l1"`, `"l2"`, `"l3"`, `"l4"`, `"l5"`, or `"l6"`. Anything else will break formatting.                                                                                                                                                                    |
| `course_number`                | A double digit number assigned to the course. Refer to the Coding Mind pamphlet. For single digit numbers, put a `"0"` before (e.g. `"01"`).                                                                                                               |
| `course_name`                  | The name of the course. This requires both an English and Chinese name.                                                                                                                                                                                    |
| `short_description`            | A description of what the course provides.                                                                                                                                                                                                                 |
| `course_content` item 0 and 1  | Describe 2 things about what students do in the course. Both require an English and Chinese translation. **For formatting reasons, do not add more than 2.**                                                                                               |
| `course_content_photo`         | A URL to an image that best represents what the course is about.                                                                                                                                                                                           |
| `course_outcomes` item 0, 1, 2 | Describe 2 things about what students are expected to have learned by the end. All items require an English and Chinese translation. **For formatting reasons, do not add more than 3.**                                                                   |
| `course_outcomes_photo`        | A URL to an image of a student's project or something that represents what we want students to make as a final project.                                                                                                                                    |
| `course_outcome_cases`         | A description of what a student who took this class before did for their final project and its significance. This requires both an English and Chinese translation.                                                                                        |
| `modules`                      | Note that this is a **List of List of JSON objects**. Be careful of formatting. Each module is its own sub-list. Each lesson is a JSON object with three fields: `"id"` representing a lesson code (e.g. `"1-1"`), and `"cn"` and `"cn"` for lesson names. |

**One very important note** is that English text must be considerably shorter than Chinese text as the same info takes up more space in English. If content doesn't fit well on a page in English, shorten the text.

The JSON follows the following format. We provide an example here that we recommend copy-pasting instead of creating it from scratch to avoid typos or formatting errors.

```json
{
    "course_level": "l1",
    "course_number": "01",
    "course_name": {
        "cn": "乐高机器人编程",
        "en": "LEGO Mindstorms Programming"
    },
    "short_description": {
        "cn": "乐高机器人课程充分发展学生的STEM能力和创新思维。",
        "en": "The LEGO robotics course fully develops students' STEM abilities and innovative thinking."
    },
    "course_content": [
        {
            "cn": "掌握机器人搭建技能",
            "en": "Master robot building skills"
        },
        {
            "cn": "学习积木编程",
            "en": "Learn block programming"
        }
    ],
    "course_content_photo": "https://assets.clevelandclinic.org/transform/cd71f4bd-81d4-45d8-a450-74df78e4477a/Apples-184940975-770x533-1_jpg",
    "course_outcomes": [
        {
            "cn": "搭建各种机器人模型",
            "en": "Build various robot models"
        },
        {
            "cn": "编程机器人任务",
            "en": "Programming robot tasks"
        },
        {
            "cn": "设计机器人解决问题",
            "en": "Design robots to solve problems"
        }
    ],
    "course_outcomes_photo": "https://assets.clevelandclinic.org/transform/cd71f4bd-81d4-45d8-a450-74df78e4477a/Apples-184940975-770x533-1_jpg",
    "course_outcome_cases": {
        "cn": "在乐高机器人课程中，小宇利用所学的搭建和编程技能设计并制作了一台可以高效叠衣服的机器人。凭借这一创新作品，他在乐高创新大赛中脱颖而出，获得了金奖。",
        "en": "In the LEGO Robotics course, Yu used the building and programming skills he learned to design and build a robot that can fold clothes efficiently. With this innovative work, he stood out in the LEGO Innovation Competition and won the gold medal."
    },
    "modules": [
        [
            {
                "id": "1-1",
                "cn": "乐高机器人简介",
                "en": "Introduction to LEGO Robotics"
            },
            {
                "id": "1-2",
                "cn": "搭建简单机器人",
                "en": "Building a Simple Robot"
            },
            {
                "id": "1-3",
                "cn": "小游戏：自动驾驶汽车",
                "en": "Mini-game: Self Driving Car"
            },
            {
                "id": "1-4",
                "cn": "为机器人添加刀片",
                "en": "Adding a Blade to Your Robot"
            }
        ],
        [
            {
                "id": "2-1",
                "cn": "搭建蝎子尾巴",
                "en": "Building the Scorpion Tail"
            },
            {
                "id": "2-2",
                "cn": "搭建腿部结构",
                "en": "Building the Legs"
            },
            {
                "id": "2-3",
                "cn": "添加爪子和传感器",
                "en": "Adding Claws and a Sensor"
            },
            {
                "id": "2-4",
                "cn": "遥控Spik3r",
                "en": "Spik3r with a Remote"
            },
            {
                "id": "2-5",
                "cn": "使用信标",
                "en": "Using a Beacon"
            },
            {
                "id": "2-6",
                "cn": "小游戏：捕捉虫子",
                "en": "Mini-game: Hunt the Bug"
            }
        ],
        [
            {
                "id": "3-1",
                "cn": "搭建抓取爪",
                "en": "Building the Gripping Claws"
            },
            {
                "id": "3-2",
                "cn": "搭建轮子",
                "en": "Building the Wheels"
            },
            {
                "id": "3-3",
                "cn": "练习运动功能",
                "en": "Practicing Movement"
            },
            {
                "id": "3-4",
                "cn": "添加遥控器",
                "en": "Adding a Remote"
            },
            {
                "id": "3-5",
                "cn": "小游戏：捡起木棍",
                "en": "Mini-game: Pick up Sticks"
            }
        ]
    ]
}
```

## Testing Locally

To test locally, perform the following:

1. Have a local version of Python installed on your machine. **None of this repository uses Python**, however Python allows an easy access to a command to run a server. A server is required in order to properly load certain components such as images and CSS. If you have another method of running an easy web server, you can avoid installing Python altogether.
2. In a terminal, change directory to the root of the cloned repository.
3. Run the terminal command `python -m http.server`.
4. Visit the following based on what you want to view:

```
http://localhost:8000/index.html?courseId={COURSE ID}&campus={CAMPUS}&lang={LANGUAGE}
```

5. To see changes, use **Ctrl + R** to reload instead of a "standard" page reload, as the CSS cache must be reloaded when viewing it locally.

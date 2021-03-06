---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Bottom App Bar
description: Display an app bar at the bottom of the screen. Used as a container for parent-related content, such as screen titles, menu items or a floating action button
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/material/bottomAppBar.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

## Constructors

```kotlin
@Composable
fun BottomAppBar(
    modifier: Modifier = Modifier,
    backgroundColor: Color = MaterialTheme.colors.primarySurface,
    contentColor: Color = contentColorFor(backgroundColor),
    fabConfiguration: FabConfiguration? = null,
    cutoutShape: Shape? = null,
    content: @Composable RowScope.() -> Unit
)
```

* **modifier** – modifier to be applied

* **content** – the content to be displayed inside of the bottom app bar
  * required

* **backgroundColor** – the background color to be applied

* **contentColor** – the color to be applied to the content inside the composable

* **fabConfiguration** – the positioning of the FAB

* **cutoutShape** – the shape to cutout for the placement of the FAB

## Examples

### Minimal Bottom App Bar
  
```kotlin
BottomAppBar {
    Text(
        text = "Jetpack Compose",
        modifier = Modifier.padding(16.dp)
    )
}
```

![Alert dialog](/academy/material/media/bottom_app_bar.png)

### Styled Bottom App Bar
  
```kotlin
BottomAppBar(
    contentColor = Color.White,
    backgroundColor = Color.Black
) {
    Text(
        text = "Jetpack Compose",
        modifier = Modifier.padding(16.dp)
    )
}
```

![Alert dialog](/academy/material/media/bottom_app_bar_styled.png)

### Bottom App Bar with FAB

```kotlin
Scaffold(
    bottomBar = {
        BottomAppBar(
            contentColor = Color.White,
            backgroundColor = Color.Black,
            cutoutShape = CircleShape
        ) {

        }
    },
    floatingActionButton = {
        FloatingActionButton(onClick = {

        }) {
            Icon(asset = Icons.Default.Done)
        }
    },
    floatingActionButtonPosition = Scaffold.FabPosition.Center,
    bodyContent = {
        bodyContent()
    })
```

![Alert dialog](/academy/material/media/bottom_app_fab.png)

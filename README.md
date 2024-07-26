# Title

## Background
On Wednesday, we were taught how to interpret data and turn it into a graph using code.

We were given demographic data taken from a real-life study - age, sex, height, etc.
- The study was measuring memory function in adults over 50 using the MRI.

With this data, we would find the links between one factor and another, to see if they correlated, by producing a graph representing the data.

## Data plotting and statistics
We wanted to find out the relationships between different factors that had been measured, such as lesion volume and lesion number, and produce the results in a graph.

We used R and ChatGPT to analyse the data. ChatGPT provided us with the code we needed simply by giving it a few instructions. R enabled us to run that code.

For example, we produced a plot to find the correlation between lesion number and BMI.

```r
# Plots the age against the number of lesions in each participant.
# The results show that as age increases, lesion number increases.

# Create the plot
ggplot(participant_data, aes(x = age, y = lesion_number)) +
  geom_point(aes(color = lesion_number), size = 5, alpha = 0.7) + # Points with color and size mappings
  geom_smooth(method = "lm", color = "blue", linetype = "solid") + # Add regression line
  scale_color_gradient(low = "lightblue", high = "darkblue") +      # Color gradient for lesion_number
  scale_size_continuous(range = c(2, 6)) +                         # Size gradient for age
  labs(title = "Correlation between Age and Lesion Number",
       x = "Age (years)",                                         # X-axis label
       y = "Lesion Number",                                       # Y-axis label
       caption = "Data Source: Your Dataset") +                   # Add a caption for the data source
  theme_light(base_size = 14) +                                   # Light theme with larger base font size
  theme(
    plot.title = element_text(hjust = 0.5, face = "bold", size = 16), # Center and bold the title with a larger size
    axis.title.x = element_text(margin = margin(t = 10), size = 14),  # Add margin and size to x-axis title
    axis.title.y = element_text(margin = margin(r = 10), size = 14),  # Add margin and size to y-axis title
    axis.text = element_text(size = 12),                           # Size of axis text
    panel.grid.major = element_line(color = "gray90", size = 0.5), # Light major grid lines
    panel.grid.minor = element_line(color = "gray95", size = 0.2)  # Light minor grid lines
  )
```

![Description](https://github.com/LK-Github-lgtm/in2science/blob/main/file_show.png)


## BMI and Lesion Number

We wanted to see if there was a relatiionship between lesion number and BMI and so we plotted a graph to show the correlation.

```r
ggplot(participant_data, aes(x = bmi, y = lesion_number)) +
  geom_point(color = "darkblue", size = 3, alpha = 0.6) +   # Adjust point color, size, and transparency
  labs(title = "Relationship between BMI and Lesion Number",
       x = "BMI",
       y = "Lesion Number") +
  theme_minimal(base_size = 15) +                            # Use a minimal theme with larger base font size
  theme(
    plot.title = element_text(hjust = 0.5, face = "bold"),   # Center the plot title and make it bold
    axis.title.x = element_text(margin = margin(t = 10)),    # Add margin to the x-axis title
    axis.title.y = element_text(margin = margin(r = 10)),    # Add margin to the y-axis title
    panel.grid.major = element_line(color = "gray80"),       # Lighten the grid lines
    panel.grid.minor = element_line(color = "gray90")        # Lighten the minor grid lines
  ) +
  geom_smooth(method = "lm", color = "red", se = FALSE, linetype = "dashed") # Add a regression line
```




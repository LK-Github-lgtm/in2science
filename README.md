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

![Description](https://github.com/LK-Github-lgtm/LK-Github-lgtm/blob/main/file_show.png)






Using ChatGPT to provide code in response to specific instructions...

Which I would then copy and paste, into Posit Cloud (R) and run it to produce the results.

To improve our plots, we provided specific instructi

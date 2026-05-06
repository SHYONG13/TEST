library(ggplot2)
library(plotly)

p <- ggplot(bigclass, aes(x = sex, y = Math, fill = sex)) +
  geom_boxplot() +
  labs(title = "Distribution of Math Scores by Gender",
       x = "Gender",
       y = "Math Score") +
  theme_minimal() +
  theme(axis.title.x = element_text(size = 18),
        axis.title.y = element_text(size = 18),
        axis.text.x = element_text(size = 14),
        axis.text.y = element_text(size = 14),
        panel.background = element_rect(fill = "white", colour = "white"),
        plot.background = element_rect(fill = "white", colour = "white"))

p_interactive <- ggplotly(p)

saveWidget(p_interactive, file = "media/plots/boxplot_math_gender.html", selfcontained = TRUE)

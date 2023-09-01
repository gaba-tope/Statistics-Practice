# 5-star_trial-probability plot

# Package & Font Import
library(ggplot2)
library(showtext)
showtext_auto()
font_add_google("Gowun Dodum", "Gowun Dodum")

# Data from "https://genshin.gamedot.org/?mid=board&target=view&board=tip&post=290"
raw <- read.csv("C:/R/Rwd/5-star prob.csv", header = F)  # Relevant File Path
colnames(raw) <- c('trial', 'probability')

# Plot
ggplot(raw, aes(x=trial, y=probability)) +
  geom_line(color="lightgrey", size= 2)+  # Line graph
  geom_point(shape=21, color="black",fill="#707070", size=1.5) + # Point
  scale_x_continuous(breaks = seq(0, 100, by = 5)) + # x axis tick interval
  scale_y_continuous(breaks = seq(0, 110, by = 10)) + # y axis tick interval
  ggtitle("캐릭터 기원 5성 출현 확률") +
  xlab("기원 횟수")+
  ylab("출현 확률") +
  theme(text=element_text(size=16,  family="Gowun Dodum"),
        plot.title = element_text(hjust = 0.5 ,size=20,family='Gowun Dodum'),
        panel.background = element_rect(fill='white', colour='black', size=1),
        panel.grid.major = element_line(size = 0.5, linetype = 'solid',
                                        colour = "#ebebeb")
        ) +
  annotate("rect", xmin = 73, xmax = 91, ymin = 5.0, ymax = 101,
           alpha = .2, fill='skyblue') +
  annotate("text", x = 80, y = 90, label = "확률 증가 구간", family="Gowun Dodum") +
  annotate("text", x = 77, y = 86, label = "(74회부터 회당 6%p 증가)", family="Gowun Dodum") +
  annotate("rect", xmin = 0, xmax = 74, ymin = -1, ymax = 1.6,
           alpha = .2, fill='lightgreen') +
  annotate("text", x= 6, y = 4, label = "1회~73회까지는 0.6% 고정 확률", family = "Gowun Dodum")

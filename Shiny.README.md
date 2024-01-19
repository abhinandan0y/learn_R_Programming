Introduction to Shiny:

Building a simple Shiny app for exploring gene expression.

```R
library(shiny)
ui <- fluidPage(
  selectInput("gene", "Select Gene:", choices = unique(gene_expression$gene)),
  plotOutput("expression_plot")
)

server <- function(input, output) {
  output$expression_plot <- renderPlot({
    ggplot(subset(gene_expression, gene == input$gene), aes(x = condition, y = counts)) + geom_point()
  })
}

shinyApp(ui, server)
```
Developing a Shiny dashboard for interactive data analysis.

```R
library(shinydashboard)
ui <- dashboardPage(
  dashboardHeader(),
  dashboardSidebar(),
  dashboardBody()
)

server <- function(input, output) {
  # Server logic goes here
}

shinyApp(ui, server)
```

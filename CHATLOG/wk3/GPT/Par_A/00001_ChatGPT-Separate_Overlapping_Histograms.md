# Separate Overlapping Histograms

#### You:
I have this histogram with 3 overlapping histograms, can you help me split it into 3 separate histograms.

fig = px.histogram(pingees, color="species", x="flipper_length_mm")
fig.show(renderer="png") # USE `fig.show(renderer="png")` FOR ALL GitHub and MarkUs SUBMISSIONS

#### ChatGPT:
Sure, I can help you split the overlapping histograms into separate ones. Below is the modified code to create three separate histograms based on the species. This assumes you have a DataFrame named `pingees` with columns `species` and `flipper_length_mm`.

```python
import plotly.express as px
import pandas as pd

# Sample DataFrame creation for demonstration
# Replace this with your actual DataFrame `pingees`
data = {
    "species": ["Adelie", "Chinstrap", "Gentoo", "Adelie", "Chinstrap", "Gentoo"],
    "flipper_length_mm": [181, 195, 210, 185, 198, 215]
}
pingees = pd.DataFrame(data)

# List of unique species
species_list = pingees["species"].unique()

# Create separate histograms for each species
for species in species_list:
    fig = px.histogram(pingees[pingees["species"] == species], x="flipper_length_mm", title=f"Histogram for {species}")
    fig.show(renderer="png")
```

In this code:

1. We extract the unique species from the `pingees` DataFrame.
2. We loop over each species and filter the DataFrame for that species.
3. For each species, we create a histogram of `flipper_length_mm` and display it.

Make sure to replace the sample DataFrame creation with your actual `pingees` DataFrame. The `fig.show(renderer="png")` will render the histograms as PNG images, suitable for GitHub and MarkUs submissions.


#### You:
Now can you help me mark the median and mean using fig.add_[h/v]line()

#### ChatGPT:
Certainly! Below is the modified code to create separate histograms for each species and mark the median and mean values using `fig.add_vline()`.

```python
import plotly.express as px
import plotly.graph_objects as go
import pandas as pd

# Sample DataFrame creation for demonstration
# Replace this with your actual DataFrame `pingees`
data = {
    "species": ["Adelie", "Chinstrap", "Gentoo", "Adelie", "Chinstrap", "Gentoo"],
    "flipper_length_mm": [181, 195, 210, 185, 198, 215]
}
pingees = pd.DataFrame(data)

# List of unique species
species_list = pingees["species"].unique()

# Create separate histograms for each species
for species in species_list:
    # Filter the DataFrame for the current species
    df_species = pingees[pingees["species"] == species]
    
    # Calculate mean and median
    mean_val = df_species["flipper_length_mm"].mean()
    median_val = df_species["flipper_length_mm"].median()
    
    # Create the histogram
    fig = px.histogram(df_species, x="flipper_length_mm", title=f"Histogram for {species}")
    
    # Add mean and median lines
    fig.add_vline(x=mean_val, line=dict(color='red', width=2, dash='dash'), annotation_text='Mean', annotation_position='top right')
    fig.add_vline(x=median_val, line=dict(color='blue', width=2, dash='dot'), annotation_text='Median', annotation_position='top left')
    
    # Show the figure
    fig.show(renderer="png")
```

In this code:

1. We filter the DataFrame for each species.
2. We calculate the mean and median of the `flipper_length_mm` column for the current species.
3. We create a histogram using `px.histogram`.
4. We add vertical lines for the mean and median using `fig.add_vline()`, with appropriate annotations.

Make sure to replace the sample DataFrame creation with your actual `pingees` DataFrame. The `fig.show(renderer="png")` will render the histograms as PNG images, suitable for GitHub and MarkUs submissions.


#### You:
Thats great, now I want to add range, interquartile range, and a range defined by two standard deviations away from the mean in both directions using fig.add_[h/v]rect()

#### ChatGPT:
Sure! Below is the modified code to create separate histograms for each species and add vertical rectangles to indicate the range, interquartile range (IQR), and the range defined by two standard deviations away from the mean in both directions using `fig.add_vrect()`.

```python
import plotly.express as px
import plotly.graph_objects as go
import pandas as pd

# Sample DataFrame creation for demonstration
# Replace this with your actual DataFrame `pingees`
data = {
    "species": ["Adelie", "Chinstrap", "Gentoo", "Adelie", "Chinstrap", "Gentoo"],
    "flipper_length_mm": [181, 195, 210, 185, 198, 215]
}
pingees = pd.DataFrame(data)

# List of unique species
species_list = pingees["species"].unique()

# Create separate histograms for each species
for species in species_list:
    # Filter the DataFrame for the current species
    df_species = pingees[pingees["species"] == species]
    
    # Calculate statistics
    mean_val = df_species["flipper_length_mm"].mean()
    median_val = df_species["flipper_length_mm"].median()
    std_val = df_species["flipper_length_mm"].std()
    min_val = df_species["flipper_length_mm"].min()
    max_val = df_species["flipper_length_mm"].max()
    q1 = df_species["flipper_length_mm"].quantile(0.25)
    q3 = df_species["flipper_length_mm"].quantile(0.75)
    
    # Define ranges
    std_range_min = mean_val - 2 * std_val
    std_range_max = mean_val + 2 * std_val
    
    # Create the histogram
    fig = px.histogram(df_species, x="flipper_length_mm", title=f"Histogram for {species}")
    
    # Add mean and median lines
    fig.add_vline(x=mean_val, line=dict(color='red', width=2, dash='dash'), annotation_text='Mean', annotation_position='top right')
    fig.add_vline(x=median_val, line=dict(color='blue', width=2, dash='dot'), annotation_text='Median', annotation_position='top left')
    
    # Add range rectangles
    fig.add_vrect(x0=min_val, x1=max_val, fillcolor="green", opacity=0.1, line_width=0, annotation_text='Range', annotation_position='top right')
    fig.add_vrect(x0=q1, x1=q3, fillcolor="yellow", opacity=0.2, line_width=0, annotation_text='IQR', annotation_position='top right')
    fig.add_vrect(x0=std_range_min, x1=std_range_max, fillcolor="purple", opacity=0.2, line_width=0, annotation_text='2 Std Dev', annotation_position='top right')
    
    # Show the figure
    fig.show(renderer="png")
```

In this code:

1. We calculate the mean, median, standard deviation, minimum, maximum, first quartile (Q1), and third quartile (Q3) for the `flipper_length_mm` column.
2. We define the range for two standard deviations away from the mean.
3. We add vertical rectangles for the overall range, IQR, and the range defined by two standard deviations using `fig.add_vrect()`.

Make sure to replace the sample DataFrame creation with your actual `pingees` DataFrame. The `fig.show(renderer="png")` will render the histograms as PNG images, suitable for GitHub and MarkUs submissions.


#### You:
It worked perfectly, can you make me the same graphs but using seaborn now please?

#### ChatGPT:
Certainly! Below is the modified code to create separate histograms for each species using Seaborn and add vertical lines and rectangles to indicate the mean, median, range, interquartile range (IQR), and the range defined by two standard deviations away from the mean in both directions.

```python
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd

# Sample DataFrame creation for demonstration
# Replace this with your actual DataFrame `pingees`
data = {
    "species": ["Adelie", "Chinstrap", "Gentoo", "Adelie", "Chinstrap", "Gentoo"],
    "flipper_length_mm": [181, 195, 210, 185, 198, 215]
}
pingees = pd.DataFrame(data)

# List of unique species
species_list = pingees["species"].unique()

# Create separate histograms for each species
for species in species_list:
    # Filter the DataFrame for the current species
    df_species = pingees[pingees["species"] == species]
    
    # Calculate statistics
    mean_val = df_species["flipper_length_mm"].mean()
    median_val = df_species["flipper_length_mm"].median()
    std_val = df_species["flipper_length_mm"].std()
    min_val = df_species["flipper_length_mm"].min()
    max_val = df_species["flipper_length_mm"].max()
    q1 = df_species["flipper_length_mm"].quantile(0.25)
    q3 = df_species["flipper_length_mm"].quantile(0.75)
    
    # Define ranges
    std_range_min = mean_val - 2 * std_val
    std_range_max = mean_val + 2 * std_val
    
    # Create the histogram
    plt.figure(figsize=(10, 6))
    sns.histplot(df_species, x="flipper_length_mm", kde=False, color="skyblue", bins=10)
    plt.title(f"Histogram for {species}")
    
    # Add mean and median lines
    plt.axvline(mean_val, color='red', linestyle='--', linewidth=2, label='Mean')
    plt.axvline(median_val, color='blue', linestyle='-.', linewidth=2, label='Median')
    
    # Add range rectangles
    plt.axvspan(min_val, max_val, color='green', alpha=0.1, label='Range')
    plt.axvspan(q1, q3, color='yellow', alpha=0.2, label='IQR')
    plt.axvspan(std_range_min, std_range_max, color='purple', alpha=0.2, label='2 Std Dev')
    
    # Add legend
    plt.legend()
    
    # Show the plot
    plt.show()
```

In this code:

1. We use Seaborn's `histplot` to create the histogram.
2. We calculate the mean, median, standard deviation, minimum, maximum, first quartile (Q1), and third quartile (Q3) for the `flipper_length_mm` column.
3. We define the range for two standard deviations away from the mean.
4. We use `plt.axvline` to add vertical lines for the mean and median.
5. We use `plt.axvspan` to add shaded areas for the overall range, IQR, and the range defined by two standard deviations.

Make sure to replace the sample DataFrame creation with your actual `pingees` DataFrame. The resulting plots will be displayed using Matplotlib's `plt.show()`.

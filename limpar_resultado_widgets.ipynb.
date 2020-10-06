
from IPython.display import display, HTML,clear_output, Javascript, Image
import ipywidgets as widgets
import matplotlib.pyplot as plt
import plotly.figure_factory as ff
import numpy as np

layoutSize = {"width":"110px"}

clear = widgets.Button(description="Limpar",
                      style= {'button_color':'#cc5105'},
                      layout=layoutSize)

plo = widgets.Button(description="Plot",
                      style= {'button_color':'#cc5105'},
                      layout=layoutSize)

resultScreen = widgets.Output()
layout = widgets.VBox([clear, plo, resultScreen])
display(layout)

def clearOut(self):
    plt.close("all")
    resultScreen.clear_output()

def plot_gra(self): 
    with resultScreen: #ESTA LINHA É O SEGREDO DE APAGAR O QUE O WIDGETS FAZ
        x1 = np.random.randn(200) - 2
        x2 = np.random.randn(200)
        x3 = np.random.randn(200) + 2
        x4 = np.random.randn(200) + 4

        hist_data = [x1, x2, x3, x4]

        group_labels = ['Group 1', 'Group 2', 'Group 3', 'Group 4']

        fig = ff.create_distplot(hist_data, group_labels, bin_size=.2)
        fig.show()
    
clear.on_click(clearOut)
plo.on_click(plot_gra)

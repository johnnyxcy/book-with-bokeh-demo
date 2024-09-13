1. 安装 selenium 和 chromedriver

```bash
python -m pip install selenium chromedriver-binary-auto
```

2. 为 bokeh 指定 chromedriver

```python
from bokeh.settings import settings

settings.chromedriver_path = "/path-to-site-packages/chromedriver_binary/chromedriver"
```

后续考虑可以做到 `mas.libs.phanpy.plotting.settings` 中

3. 输出图形

```python
from bokeh.io.export import get_screenshot_as_png
p.height = 300
p.width = 300
get_screenshot_as_png(p)
```

后续可以考虑将这个做到 `BasePlot.show()` 中，`plot_settings.output_backend_in_nb = "png" | "javascript" | "png+chromedriver"`

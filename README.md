### This is a customization to fit in Agiplan Pie Chart needs.

> Original repo: https://github.com/PhilJay/MPAndroidChart

![Pie Chart](./pie-chart.png)

## Installation

### Gradle

```
dependencies {
	compile 'com.github.ilegra:Agiplan-Charts-Android:4.0.1'
}
```


## Usage example
```java
public class InvestmentChartActivity extends Activity {

    private InvestmentPieChart mChart;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_investment_chart);

        mChart = (InvestmentPieChart) findViewById(R.id.investment_chart);

        ArrayList<InvestmentPieEntry> entries = new ArrayList<InvestmentPieEntry>();

        entries.add(new InvestmentPieEntry(50f, getMockedText(), this.getResources().getColor(R.color.pie_graph_color_primary), this.getResources().getDrawable(R.drawable.graph_circle_highlight_primary)));
        entries.add(new InvestmentPieEntry(20f, getMockedText(), this.getResources().getColor(R.color.pie_graph_color_blue), this.getResources().getDrawable(R.drawable.graph_circle_highlight_blue)));
        entries.add(new InvestmentPieEntry(20f, getMockedText(), this.getResources().getColor(R.color.pie_graph_color_green), this.getResources().getDrawable(R.drawable.graph_circle_highlight_green)));
        entries.add(new InvestmentPieEntry(10f, getMockedText(), this.getResources().getColor(R.color.pie_graph_color_green), this.getResources().getDrawable(R.drawable.graph_circle_highlight_green)));

        MarkerView markView = new InvestmentMarkerView(this, R.layout.pie_chart_marker, R.id.investment_chart_description, R.id.vertical_line_graph, R.id.percentage_value_graph);

        mChart.loadChart(entries, generateCenterSpannableText(), markView);
    }

    private SpannableString generateCenterSpannableText() {
        SpannableString s = new SpannableString("Total Investido\nR$212.890,69");
        s.setSpan(new RelativeSizeSpan(1.2f), 0, 15, 0);
        s.setSpan(new RelativeSizeSpan(1.2f), 16, 18, 0);
        s.setSpan(new RelativeSizeSpan(2.8f), 18, 25, 0);
        s.setSpan(new RelativeSizeSpan(1.2f), 25, s.length(), 0);
        s.setSpan(new StyleSpan(Typeface.BOLD), 18, 25, 0);
        s.setSpan(new ForegroundColorSpan(Color.WHITE), 0, s.length(), 0);
        return s;
    }

    private SpannableString getMockedText() {
        SpannableString s = new SpannableString("CDB Banco Agiplan\nR$212.890,69");
        return s;
    }
```

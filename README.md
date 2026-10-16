![salesanalysis](sales_analysis2.jpg)
# SALES PERFOMANCE ANALYSIS

## PROJECT OVERVIEW
This project turns three years of order-level sales records into an interactive Excel dashboard that management can use to see, at a glance, how the business is performing. The dataset covers 444 orders placed between 2013 and 2015 across four regions, five salespeople and four frozen dessert product lines.
Across the period, the business recorded total sales of $3,254,576.95 from 2,322,594 units sold. Revenue rose by 12.9% from 2013 to 2014 and then slipped by 2.8% in 2015, which suggests growth has stalled rather than continued.
The main findings are:
•Ice Cream is the anchor product. It brings in 42.4% of all revenue, well ahead of Tasty Treats (25.8%), Frozen Yogurt (20.0%) and Popsicles (11.8%).
•The Central region leads by a wide margin. It generates 42.8% of revenue, although it is also the only region served by two salespeople.
•Performance varies widely between salespeople. Parker is the top earner at $760,122.80, while Pullen trails at $505,968.95, a gap of about $254,000.
•Sales are strongly seasonal. April is the strongest month in every year, while November and December are consistently the weakest of the months recorded.
The report also highlights several data quality points that should be confirmed before the numbers are used for major decisions, most importantly the large number of near-identical order lines and the absence of June to October in the data. These are covered in the Limitations section.
## BUSINESS PROBLEM
Sales information was held in a long, flat list of 444 order lines. In that form it is difficult to answer even simple management questions, such as which region earns the most, which product is carrying the business, or whether sales are growing from year to year. Totals had to be worked out by hand, which is slow, repeatable only with effort, and open to error.
Without a clear and consistent view of performance, managers cannot easily:
•compare the contribution of each region, product line and salesperson;
•identify seasonal peaks and slow periods in order to plan stock and staffing; or
•track whether the business is growing, flat or declining over time.
This project addresses that gap by organizing the raw records into a structured dataset and presenting the key results in a single, interactive dashboard.

## OBJECTIVE

To build an interactive Excel dashboard that summarizes sales performance for 2013 to 2015 and supports faster, evidence-based decisions.
Specific objectives
1.Review and prepare the raw sales data so that it is reliable and ready for analysis.
2.Calculate headline measures: total sales, total units sold and total number of transactions.
3.Analyze revenue by year, month, region, product type and salesperson.
4.Present the results in clear charts that can be filtered by Year, Type, Salesperson and Region.
5.Draw out key findings and make practical recommendations for management.
5.Draw out key findings and make practical recommendations for management.

## DATASET DESCRIPTION

The data is stored in the workbook EXCEL_REAL_DASHBOARD.xlsx. The “raw data” sheet holds the original records, and the “SALES” sheet holds an identical copy that has been formatted as an Excel Table named sales. This table is the single source for every PivotTable in the workbook.
The dataset contains 444 records and 8 fields, covering 148 orders in each of the three years (2013, 2014 and 2015). Every record represents one order line.

**|FIELD | DATA  TYPE | DESCRIPTION |** 

| Year | number | Calendar of the year (2013, 2014, 2015) | 

| month | text | month of the order ( seven month; January to may, November and December | 

| type | text | product line ice cream, frozen yoghurt, popsicle or tasty treat | 

| salesperson | text | person in charge; bishop, parker, lee, Pullen and Watson |

| Region | text | Sales region: Central, North, South or West |

| sales | Currency ($) | Value of the order line in US dollars.| 

| unit | number | Number of units sold on the order line.

| order | text | Order identifier from 001 to 444, stored as text so that leading zeros are kept.

Each salesperson works in only one region: Bishop in the West, Parker in the North, Pullen in the South, and both Lee and Watson in the Central region. This means salesperson and region results overlap closely and should be read together.

**DATA CLEANING**

Before any analysis, the data was checked for the common problems that distort results. The checks and outcomes are summarized below.

**| Check | outcome |**

| missing value | None. All 444 records are complete across all 8 fields.| 

| Category spelling and consistency | Category spelling and consistency |	Clean. Year, Month, Type, Salesperson and Region each contain a small, consistent set of values with no spelling variants or stray spaces.|

| Data types | 	Correct. Year, Sales and Units are numeric; Order # is text so that identifiers such as 001 are not shortened to 1| 

| Unique identifiers |	Every Order # is unique, so there is no repeated order number.|

| Consistency between sheets | The raw data sheet and the SALES table match exactly, record for record.|

| Sales values |
|350 of the 444 Sales values are calculated in Excel as Units multiplied by a fixed rate (1.25, 1.4 or 1.5). The other 94 are typed values. Twelve records show an implied price per unit outside those three rates (for example, $4,666 for 5,623 units).| 

| Near-duplicate records |	218 records are identical to another record in every field except Order #. These were flagged but kept, because they carry distinct order numbers and cannot be proven to be errors from the data alone.|

No records were deleted or altered during cleaning, which is why the dashboard reports 444 transactions. Decisions on the duplicate and manually entered values are left to the data owner and are discussed under Limitations.



## DATA PREPARATION

Once the data was confirmed to be usable, it was prepared for analysis and reporting in the following steps.
1.Converted the data into an Excel Table. The records were formatted as a table named sales. A table expands automatically when new rows are added, so every connected summary stays up to date.
2.Protected the order identifiers. Order # was kept as text to preserve leading zeros.
3.Applied currency formatting. The Sales column uses a dollar format with two decimal places for consistency across the workbook.
4.Built the PivotTables. Five PivotTables were created from the sales table, each summing Sales by one dimension: Year, Month, Region, Type and Salesperson. Each is placed on its own sheet (YEARLY REVENUE, MONTHLY REVENUE, REGIONAL REVENUE, REVENUE BY TYPE and SALESPERSON REVENUE).
5.Created the headline measures. Three formulas on the dashboard sheet total the Sales column, the Units column and the number of transactions.
6.Added slicers. Four slicers (Year, Type, Salesperson and Region) were added so that users can filter the dashboard with a click.

## DATASET DESCRIPTION

The analysis summarizes revenue along each dimension and compares the contribution of each group. All shares are calculated against total sales of $3,254,576.95.
## Overall performance

| Measure |	Value |

| Total sales |	$3,254,576.95 |

| Total units | sold	2,322,594 |

| Total transactions |	444 | 

| Average sales per transaction |	$7,330.13 |
| Average units per transaction |	5,231
| Average price per unit |	$1.40

**yearly revenue**

**|Year |	Revenue |	Share |	Change vs prior year**

| 2013 |	$1,008,662.75 |	31.0% |	– 

| 2014 |	$1,138,686.00 |	35.0% |	+12.9% 

| 2015 |	$1,107,228.20 |	34.0%	| –2.8% 

| Total |	$3,254,576.95 |	100.0% |	

Revenue grew strongly in 2014 and fell slightly in 2015. Units sold were identical in all three years (774,198), so the movement in revenue comes entirely from the value per order line, not from selling more.

**Revenue by month**

| Month |	Revenue |	Share |	Orders |

| January |	$513,336.00 |	15.8% |	60 |

| February |	$521,344.75 |	16.0% |	54 |

| March |	$423,204.70 |	13.0% |	60 |

| April |	$640,494.40 |	19.7% |	90 |

| May |	$428,512.40 |	13.2% |	66 |

| November | $383,151.70 |	11.8% |	60 |

| December |	$344,533.00 |	10.6% |	54 |

| Total |	$3,254,576.95 |	100.0% |	444 |

April alone contributes 19.7% of all revenue and has the highest order count. January to May together produce $2,526,892.25, compared with $727,684.70 for November and December combined. These totals add up three years of data and cover only the seven months available.

**Revenue by region**

|Region |	Revenue |	Share |	Orders | Avg per order

|Central |	$1,391,555.30 |	42.8% |	168 |	$8,283

| North |	$760,122.80 |	23.4% |	102 |	$7,452

| West |	$596,929.90 |	18.3% |	90 |	$6,633

| South |	$505,968.95 |	15.5% |	84 |	$6,023

| Total |	$3,254,576.95 |	100.0% |	444 |	$7,330














- orange
- mangoe
- pawpaw
**i am coming**
*iam coming*
***i am coming***

~i have startes leaening~

~~i am learning~~

1.
2.

[google](https://google.com)

![my dashboard](dashboard.png)








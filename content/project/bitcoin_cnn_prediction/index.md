---
title: Bitcoin Buy/Sell predictions Using Convolutional Neural Network
summary: Modified Implementation of the research paper titled "Algorithmic Financial Trading with Deep Convolutional Neural Networks Time Series to Image Conversion Approach", in order to specifically adapt it to Bitcoin price predictions.
tags:
- Bitcoin
- Deep Learning
- Convolutional Neural Network
- Financial Machine Learning

date: "2021-06-01T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Photo by Executium on Unsplash
  focal_point: Smart

links:
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
# slides: example
---


# Bitcoin Buy/Sell predictions Using Convolutional Neural Network

Modified Implementation of the research paper titled "Algorithmic Financial Trading with Deep Convolutional Neural Networks: Time Series to Image Conversion Approach", in order to specifically adapt it to Bitcoin price predictions.

As far as I know, this is the first attempt to predict the price of bitcoin using a Convolutional Neural Network.
The main features used are composed of the Bitcoin close price and some features derived directly from the Bitcoin Blockchain, in particular:
 - Active Addresses
 - Addresses with Non-Zero Balance
 - Addresses with Balance >= 1k BTC
 - Addresses with Balance >= 10k BTC
 - Balance on Exchanges
 - Exchange Net Flow Volume
 - Fee Ratio Multiple (FRM) More info
 - Thermocap (and not Marketcap to Thermocap Ratio)
 - Coin Days Destroyed (CDD) More info
 - Cumulative Value-Days Destroyed (CVDD) More info
 - Dormancy More info
 - Entity-adjusted Dormancy Flow
 - Liveliness More info
 - Percent of Supply Last Active 1+ Years Ago
 - Realized HODL (RHODL) Ratio More info
 - Realized Profit/Loss Ratio More info
 - Difficulty Ribbon Ccompression
 - Adjusted Spent Output Ratio (aSOPR) More info
 - Stock to Flow Deflection
 - Percent Supply in Profit More info
 - Net Unrealized Profit/Loss (NUPL) More info

On all of these I went to measure a series of Technical Indicators for different time-frames, so as to increase the amount of information, and also keep knowledge of the past. Then these will be used to compose the convolutional neural network images through Recurrence Plots.

The labelling was done following the Triple Barrier, the strategy devised by Marcos Lopez De Prado, and explained in Advances in Financial Machine Learning. This strategy should simulate a Take Profit and Stop Loss scheme, using horizontal and vertical bars.  To simplify the classification, I chose to make the problem binary; the model should learn which days are best to buy bitcoin and which days are best to sell. Afterwards it will be task of the trading strategy applied on these information to have to take advantage of the predictions at best.

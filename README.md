Laravel Sentiment Analysis
===============


[![Build Status](https://img.shields.io/travis/AntoineAugusti/laravel-sentiment-analysis/master.svg?style=flat)](https://travis-ci.org/AntoineAugusti/laravel-sentiment-analysis)
[![Software License](https://img.shields.io/badge/license-Apache%202.0-brightgreen.svg?style=flat)](LICENSE.md)
[![Latest Version](https://img.shields.io/github/release/AntoineAugusti/laravel-sentiment-analysis.svg?style=flat)](https://github.com/AntoineAugusti/laravel-sentiment-analysis/releases)

## Introduction
A Laravel wrapper for [phpInsight](https://github.com/JWHennessey/phpInsight).

## Installation

[PHP](https://php.net) 5.4+ or [HHVM](http://hhvm.com) 3.2+, and [Composer](https://getcomposer.org) are required.

To get the latest version of Laravel Sentiment Analysis, simply require `"antoineaugusti/laravel-sentiment-analysis": "1.0.*"` in your `composer.json` file. You'll then need to run `composer install` or `composer update` to download it and have the autoloader updated.

Once Laravel Sentiment Analysis is installed, you need to register the service provider. Open up `app/config/app.php` and add the following to the `providers` key.

* `'Antoineaugusti\LaravelSentimentAnalysis\LaravelSentimentAnalysisServiceProvider'`

You can register the SentimentAnalysis facade in the `aliases` key of your `app/config/app.php` file if you like.

* `'SentimentAnalysis' => 'Antoineaugusti\LaravelSentimentAnalysis\Facades\SentimentAnalysis'`

## Usage
Sentences can be classified as **negative**, **neutral** or **positive**. The only supported language for the moment is **English**.

### SentimentAnalysis::isNegative($sentence)
Returns a boolean telling if the given `$sentence` is classified as negative.

### SentimentAnalysis::isNeutral($sentence)
Returns a boolean telling if the given `$sentence` is classified as neutral.

### SentimentAnalysis::isPositive($sentence)
Returns a boolean telling if the given `$sentence` is classified as positive.

### SentimentAnalysis::decision($sentence)
Get the sentiment of a sentence. Will return `negative`, `neutral` or `positive`

### SentimentAnalysis::score($sentence)
Get the confidence of a decision for a result. The closer to 1, the better!
# QHSE REST API

{% swagger baseUrl="https://qhse-professionals.nl" path="/wp-json/qhsejobs/v1/job/:jobid" method="get" summary="Get Job" %}
{% swagger-description %}
This endpoint allows you to get free cakes.
{% endswagger-description %}

{% swagger-parameter in="path" name="jobid" type="string" %}
ID of the job to get.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
Authentication token to track down who is emptying our stocks.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="recipe" type="string" %}
The API will do its best to find a cake matching the provided recipe.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="gluten" type="boolean" %}
Whether the cake should be gluten-free or not.
{% endswagger-parameter %}

{% swagger-response status="200" description="Cake successfully retrieved." %}
```javascript
{
    "name": "Cake's name",
    "recipe": "Cake's recipe name",
    "cake": "Binary cake"
}
```
{% endswagger-response %}

{% swagger-response status="404" description="Could not find a cake matching this query." %}
```javascript
{
    "message": "Ain't no cake like that."
}
```
{% endswagger-response %}
{% endswagger %}

[![Build Status](https://circleci.com/gh/mikevdberge/qhse-jobs-api/tree/master.svg?style=shield\&circle-token=a2c6f7ffef5ccf3e9a7982c14b945f583f89c072)](https://circleci.com/gh/mikevdberge/qhse-jobs-api/tree/master)[!API Status](https://img.shields.io/uptimerobot/status/m783115057-d310c118d45e6c2dec230ad0.svg)

## API Description

### [API Blueprint](http://apiblueprint.org)

* Document: [apiary.apib](https://github.com/mikevdberge/qhse-jobs-api/tree/51ad04a95024b758368831c179db648e3d713417/apiary.apib)
* Dredd configuration: [dredd.yml](https://github.com/mikevdberge/qhse-jobs-api/tree/51ad04a95024b758368831c179db648e3d713417/dredd.yml)

## CI Status

| CI                               | Configuration                                                                                                                           | Status                                                                                                                                                                                       |
| -------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [CircleCI](https://circleci.com) | [.circleci/config.yml](https://github.com/mikevdberge/qhse-jobs-api/tree/51ad04a95024b758368831c179db648e3d713417/.circleci/config.yml) | [![](https://circleci.com/gh/mikevdberge/qhse-jobs-api/tree/master.svg?style=svg\&circle-token=a2c6f7ffef5ccf3e9a7982c14b945f583f89c072)](https://circleci.com/gh/mikevdberge/qhse-jobs-api) |

# QHSE REST API

{% api-method method="get" host="https://qhse-professionals.nl" path="/wp-json/qhsejobs/v1/job/:jobid" %}
{% api-method-summary %}
Get Job
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get free cakes.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="jobid" type="string" %}
ID of the job to get.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authentication token to track down who is emptying our stocks.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="recipe" type="string" %}
The API will do its best to find a cake matching the provided recipe.
{% endapi-method-parameter %}

{% api-method-parameter name="gluten" type="boolean" %}
Whether the cake should be gluten-free or not.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    "name": "Cake's name",
    "recipe": "Cake's recipe name",
    "cake": "Binary cake"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```javascript
{
    "message": "Ain't no cake like that."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

[![Build Status](https://circleci.com/gh/mikevdberge/qhse-jobs-api/tree/master.svg?style=shield&circle-token=a2c6f7ffef5ccf3e9a7982c14b945f583f89c072)](https://circleci.com/gh/mikevdberge/qhse-jobs-api/tree/master)[!API Status](https://img.shields.io/uptimerobot/status/m783115057-d310c118d45e6c2dec230ad0.svg)

## API Description

### [API Blueprint](http://apiblueprint.org/)

* Document: [apiary.apib](https://github.com/mikevdberge/qhse-jobs-api/tree/51ad04a95024b758368831c179db648e3d713417/apiary.apib)
* Dredd configuration: [dredd.yml](https://github.com/mikevdberge/qhse-jobs-api/tree/51ad04a95024b758368831c179db648e3d713417/dredd.yml)

## CI Status

| CI | Configuration | Status |
| :--- | :--- | :--- |
| [CircleCI](https://circleci.com/) | [.circleci/config.yml](https://github.com/mikevdberge/qhse-jobs-api/tree/51ad04a95024b758368831c179db648e3d713417/.circleci/config.yml) | [![](https://circleci.com/gh/mikevdberge/qhse-jobs-api/tree/master.svg?style=svg&circle-token=a2c6f7ffef5ccf3e9a7982c14b945f583f89c072)](https://circleci.com/gh/mikevdberge/qhse-jobs-api) |


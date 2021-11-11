# GET Job

{% swagger baseUrl="https://qhse-professionals.nl" path="/wp-json/v1/jobs/:id" method="get" summary="Get Job" %}
{% swagger-description %}
This endpoint allows you to get free cakes.
{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" %}
ID of the job to get, for free of course.
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


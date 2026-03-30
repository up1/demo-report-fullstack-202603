# Frontend development with React and Tailwind CSS


## Technologies 
* React with Vite
* Tailwind CSS
* Axios for API calls

## Key Features
* User-friendly interface for submitting reports
* Responsive design with Tailwind CSS
* Integration with backend API for report submission


## User Interface
* A form for users to input their report details
* A submit button to send the report to the backend
* Feedback messages for successful submission or errors

Use UI design from [Pencil project](https://docs.pencil.dev/getting-started/ai-integration)


## API Integration
* Use Axios to send POST requests to the backend API endpoint
  * Call to `http://localhost:3000/api/report` with the user's input as the request body
* Handle responses and display appropriate feedback to the user
  * 200 OK: Report submitted successfully
  * 400 Bad Request: Invalid input data
  * 500 Internal Server Error: Server issues, try again later


## REST API Endpoints
* Success case (200 OK)
  * Results with dynamic column names and values
  * Pagination information (page number and size)
* Data not found case (404 Not Found)
  * Message indicating data not found
* System error case (500 Internal Server Error)
  * Message indicating system error

```
POST /api/report
HTTP Request body
{
  "question": "<input>"
}

HTTP Response with JSON format
code=200 with dynamic column_name and value
{
    "results"[
        "column_name_1": "value1",
        "column_name_2": "value2",
        "column_name_3": "value3",
    ],
    "page_no": 1,
    "size": 10
}

code=404 with data not found
{
   "message": "Data not found"
}

code=500
{
   "message": "System error"
}
```
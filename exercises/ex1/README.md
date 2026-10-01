# Introducing to SAP-RPT-1

SAP-RPT-1 (Relational Pre-trained Transformer) is SAP's first relational foundation model. Unlike large language models that operate on unstructured text, SAP-RPT-1 is table-native — built to understand and reason over structured relational business data. It supports in-context learning, meaning you can use it out of the box to extract business insights from your data with no model training or fine-tuning required.

More details about SAP-RPT-1 can be found in the SAP AI Golden Path(https://architecture.learning.sap.com/docs/golden-path/ai-golden-path/build-and-deliver/predictive-tabular-ai?_highlight=rpt#how-to-get-started-with-sap-rpt-1).

In this exercise, we will create...

## Exercise 1.1 Sub Exercise 1 Description

After completing these steps you will have created...

1. Click here.
<br>![](/exercises/ex1/images/01_01_0010.png)

2.	Insert this line of code.
```abap
response->set_text( |Hello World! | ). 
```



## Exercise 1.2 Sub Exercise 2 Description

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc <> 0.
    response->set_status( i_code = 400
                     i_reason = 'Bad request').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex1/images/01_02_0010.png)


## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)


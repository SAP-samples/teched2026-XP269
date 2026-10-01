# Introducing to SAP-RPT-1

SAP-RPT-1 (Relational Pre-trained Transformer) is SAP's first relational foundation model. Unlike large language models that operate on unstructured text, SAP-RPT-1 is table-native — built to understand and reason over structured relational business data. It supports in-context learning, meaning you can use it out of the box to extract business insights from your data with no model training or fine-tuning required.

More details about SAP-RPT-1 can be found in the SAP AI Golden Path(https://architecture.learning.sap.com/docs/golden-path/ai-golden-path/build-and-deliver/predictive-tabular-ai?_highlight=rpt#how-to-get-started-with-sap-rpt-1).

## Level 2 Heading

After completing these steps you will have....

1.	Click here.
<br>![](/exercises/ex0/images/00_00_0010.png)

2.	Insert this code.
``` abap
 DATA(params) = request->get_form_fields(  ).
 READ TABLE params REFERENCE INTO DATA(param) WITH KEY name = 'cmd'.
  IF sy-subrc <> 0.
    response->set_status( i_code = 400
                     i_reason = 'Bad request').
    RETURN.
  ENDIF.
```

## Summary

Now that you have ... 
Continue to - [Exercise 1 - Exercise 1 Description](../ex1/README.md)

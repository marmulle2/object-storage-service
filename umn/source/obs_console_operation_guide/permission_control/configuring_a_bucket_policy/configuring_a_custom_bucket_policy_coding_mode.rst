:original_name: obs_03_0141.html

.. _obs_03_0141:

Configuring a Custom Bucket Policy (Coding Mode)
================================================

You can configure a custom bucket policy by coding. The size of a custom bucket policy cannot exceed 20 KB.

Procedure
---------

#. In the bucket list, click the bucket you want to operate. The **Overview** page is displayed.

#. In the navigation pane, choose **Permissions**.

#. On the **Bucket Policies** tab page, configure a custom bucket policy according to your needs.

   On the right of **Custom Bucket Policies**, select **Coding mode** to configure the policy in the coding mode.

#. The following is an example policy edited in JSON:

   .. code-block::

      {
         "Statement":[
             {
                 "Action":[
                     "CreateBucket",
                     "DeleteBucket"
                 ],
                 "Effect":"Allow",
                 "Principal":{
                     "ID":[
                         "domain/account ID",
                         "domain/account ID:user/User ID"
                     ]
                 },
                 "Condition":{
                     "NumericNotEquals":{
                         "Referer":"sdf"
                     },
                     "StringNotLike":{
                         "Delimiter":"ouio"
                     }
                 },
                 "Resource":"000-02/key01"
             }
         ]
       }

   .. table:: **Table 1** Parameter description

      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                    |
      +===================================+================================================================================================================================================================================================+
      | Action                            | Actions the bucket policy applies to. For details, see :ref:`Actions <obs_03_0051>`.                                                                                                           |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Effect                            | Effect of the bucket policy. For details, see :ref:`Effect <obs_03_0115>`.                                                                                                                     |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Principal                         | Authorized users on whom the bucket policy takes effect. You can obtain the user ID on the **My Credential** page by logging in to the console as the user to be authorized. Principal format: |
      |                                   |                                                                                                                                                                                                |
      |                                   | -  "domain/*account ID*" (when the principal is an account)                                                                                                                                    |
      |                                   | -  "domain/*account ID*:user/*User ID*" (when the principal is a user under an account)                                                                                                        |
      |                                   |                                                                                                                                                                                                |
      |                                   | .. note::                                                                                                                                                                                      |
      |                                   |                                                                                                                                                                                                |
      |                                   |    For **Account ID**, enter the **Domain ID** that can be found on the **My Credential** page.                                                                                                |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Condition                         | Conditions under which the bucket policy takes effect. For details, see :ref:`Conditions <obs_03_0120>`.                                                                                       |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Resource                          | Resources on which the bucket policy takes effect. For details, see :ref:`Resources <obs_03_0118>`.                                                                                            |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **Save**.

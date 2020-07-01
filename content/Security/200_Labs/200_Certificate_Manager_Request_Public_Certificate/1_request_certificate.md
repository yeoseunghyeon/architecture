---
title: "Requesting a public certificate using the console"
date: 2020-04-24T11:16:09-04:00
chapter: false
weight: 1
pre: "<b>1. </b>"
---

1. Sign into the AWS Management Console and open the ACM console at [https://console.aws.amazon.com/acm/home](https://console.aws.amazon.com/acm/home). Select your prefferred region for regional certificates including Elastic Load Balancing, or *US East (N. Virginia)* for global services including Amazon CloudFront.
2. If you see a welcome page, click **Get started** under *provision certificates* area.
3. On the Request a certificate page, click *Request a public certificate*, then click **Request a certificate**.
4. Type your domain name. You can use a fully qualified domain name (FQDN) such as `www.example.com` or a bare or apex domain name such as `example.com`. You can also use an asterisk `*` as a wildcard in the leftmost position to protect several site names in the same domain. For example, `*.example.com` protects `corp.example.com`, and `images.example.com`. The wildcard name will appear in the Subject field and the Subject Alternative Name extension of the ACM certificate.

    **Note:** When you request a wildcard certificate, the asterisk `*` must be in the leftmost position of the domain name and can protect only one subdomain level. For example, `*.example.com` can protect `login.example.com`, and `test.example.com`, but it cannot protect `test.login.example.com`. Also note that `*.example.com` protects only the subdomains of `example.com`, it does not protect the bare or apex domain `example.com`. To protect both, see the next step.

5. To add more domain names to the ACM certificate, choose **Add another name to this certificate**  and type another domain name in the text box that opens. This is useful for protecting both a bare or apex domain (like `example.com`) and its subdomains `*.example.com`.
6. After you have typed valid domain names, choose **Next**.
7. Before ACM issues a certificate, it validates that you own or control the domain names in your certificate request. You can use either email validation or DNS validation. If you choose email validation, ACM sends validation email to three contact addresses registered in the WHOIS database and to five common system administration addresses for each domain name. You or an authorized representative must approve one of these email messages. If you use DNS validation, you simply create a CNAME record provided by ACM to your DNS configuration. Choose your option, then click **Review**.

    **Note:** If you are able to edit your DNS configuration, we recommend that you use DNS domain validation rather than email validation. DNS validation has multiple benefits over email validation. See Use DNS to Validate Domain Ownership.

 7. If the review page correctly contains the information that you provided for your request, choose **Confirm and request**. The following page shows that your request status is pending validation. You must approve the request either through email link or DNS record.

    **Important:** Unless you choose to opt out, your certificate will be automatically recorded in at least two public certificate transparency databases. You cannot currently use the console to opt out. You must use the AWS CLI or the API. For more information, see [Opting Out of Certificate Transparency Logging](https://docs.aws.amazon.com/acm/latest/userguide/acm-bestpractices.html#best-practices-transparency). For general information about transparency logs, see [Certificate Transparency Logging](https://docs.aws.amazon.com/acm/latest/userguide/acm-concepts.html#concept-transparency).
8. Your certificate is now ready to associate with a [supported service](https://docs.aws.amazon.com/en_pv/acm/latest/userguide/acm-services.html).

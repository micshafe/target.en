---
description: Information about issues customers face when using cloud-based instances to test Adobe Target.
keywords: cloud instances;public suffix list;public suffix;cookie;first-party cookie;1st-party cookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
seo-description: Information about issues customers face when using cloud-based instances to test Adobe Target.
seo-title: Using Cloud-Based Instances with Target
solution: Target
title: Using Cloud-Based Instances with Target
uuid: 8ecdcc27-2feb-4041-b123-d515d07cfb55
index: y
internal: n
snippet: y
translate: y
---

# Using Cloud-Based Instances with Target

Target customers sometimes use cloud-based instances with `Target` for testing or simple proof-of-concept purposes. These instances might include the following domains: 

<table id="simpletable_9C9D8225552A483F958D0F4AF7CEA31A"> 
 <tr class="strow">
  <td class="stentry"> <p>azurewebsites.net</p></td>
  <td class="stentry"> <p>cloudapp.net</p></td>
  <td class="stentry"> <p>amazonaws.com</p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>cloudfront.net</p></td>
  <td class="stentry"> <p>herokuapp.com</p></td>
  <td class="stentry"> <p>firebaseapp.com</p></td> 
 </tr> 
</table>

These domains, and many others, are part of the [Public Suffix List](https://publicsuffix.org/list/public_suffix_list.dat). 
**Issue:**Modern browsers won't save cookies if you are using these domains. 
The `at.js` and `mbox.js` JavaScript libraries use cookies to track users to ensure that `Target` always presents a consistent experience. If the `Target` JavaScript libraries can't save cookies, `Target` requests are disabled. 
**Solution:**As best practice, if you intend to use cloud-based instances with domains included on the Public Suffix List, make sure that you customize the `cookieDomain` setting. For more information, see [targetGlobalSettings()](c_target-ats-functions.md#concept_8DACBC47ABDE4279BB102B42609FE506). 
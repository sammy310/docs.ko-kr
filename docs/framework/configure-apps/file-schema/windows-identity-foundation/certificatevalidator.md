---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 3f3d79d3567c1714a79423b7767ce3f454b9d52d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152790"
---
# <a name="certificatevalidator"></a>\<인증서유효성 검사자>
인증서 유효성 검사에 대한 사용자 지정 형식을 지정합니다. 이 형식은 [ \<인증서](certificatevalidation.md) `certificateValidationMode` 유효성 검사>요소의 특성이 "사용자 지정"으로 설정된 경우에만 사용됩니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<ID구성>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<인증서 유효성 검사>**](certificatevalidation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<인증서유효성>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation>  
      <certificateValidator type=xs:string>  
      </certificateValidator>  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|type|<xref:System.IdentityModel.Selectors.X509CertificateValidator> 클래스에서 파생되는 사용자 지정 형식을 지정합니다. 이 `certificateValidationMode` 형식을 사용 하려면 [인증서유효성>요소의 특성을 "사용자 지정"으로 설정 \<](certificatevalidation.md) 합니다. 특성을 지정하는 방법에 대한 자세한 내용은 [사용자 지정 유형 참조](../windows-workflow-foundation/index.md)를 참조하십시오. `type` (선택 사항)|  
  
### <a name="child-elements"></a>자식 요소  
 None  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<인증서 유효성 검사>](certificatevalidation.md)|토큰 처리기가 인증서의 유효성을 검사하는 데 사용하는 설정을 제어합니다.|  
  
## <a name="example"></a>예제  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```

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
# <a name="certificatevalidator"></a><span data-ttu-id="8ba0b-101">\<인증서유효성 검사자></span><span class="sxs-lookup"><span data-stu-id="8ba0b-101">\<certificateValidator></span></span>
<span data-ttu-id="8ba0b-102">인증서 유효성 검사에 대한 사용자 지정 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba0b-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="8ba0b-103">이 형식은 [ \<인증서](certificatevalidation.md) `certificateValidationMode` 유효성 검사>요소의 특성이 "사용자 지정"으로 설정된 경우에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ba0b-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
<span data-ttu-id="8ba0b-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8ba0b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8ba0b-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="8ba0b-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="8ba0b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<ID구성>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="8ba0b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="8ba0b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<인증서 유효성 검사>**](certificatevalidation.md)</span><span class="sxs-lookup"><span data-stu-id="8ba0b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)</span></span>\
<span data-ttu-id="8ba0b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<인증서유효성>**</span><span class="sxs-lookup"><span data-stu-id="8ba0b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ba0b-109">구문</span><span class="sxs-lookup"><span data-stu-id="8ba0b-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ba0b-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8ba0b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8ba0b-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba0b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ba0b-112">특성</span><span class="sxs-lookup"><span data-stu-id="8ba0b-112">Attributes</span></span>  
  
|<span data-ttu-id="8ba0b-113">attribute</span><span class="sxs-lookup"><span data-stu-id="8ba0b-113">Attribute</span></span>|<span data-ttu-id="8ba0b-114">Description</span><span class="sxs-lookup"><span data-stu-id="8ba0b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ba0b-115">type</span><span class="sxs-lookup"><span data-stu-id="8ba0b-115">type</span></span>|<span data-ttu-id="8ba0b-116"><xref:System.IdentityModel.Selectors.X509CertificateValidator> 클래스에서 파생되는 사용자 지정 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba0b-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="8ba0b-117">이 `certificateValidationMode` 형식을 사용 하려면 [인증서유효성>요소의 특성을 "사용자 지정"으로 설정 \<](certificatevalidation.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba0b-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="8ba0b-118">특성을 지정하는 방법에 대한 자세한 내용은 [사용자 지정 유형 참조](../windows-workflow-foundation/index.md)를 참조하십시오. `type`</span><span class="sxs-lookup"><span data-stu-id="8ba0b-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="8ba0b-119">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="8ba0b-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ba0b-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8ba0b-120">Child Elements</span></span>  
 <span data-ttu-id="8ba0b-121">None</span><span class="sxs-lookup"><span data-stu-id="8ba0b-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ba0b-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8ba0b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8ba0b-123">요소</span><span class="sxs-lookup"><span data-stu-id="8ba0b-123">Element</span></span>|<span data-ttu-id="8ba0b-124">Description</span><span class="sxs-lookup"><span data-stu-id="8ba0b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ba0b-125">\<인증서 유효성 검사></span><span class="sxs-lookup"><span data-stu-id="8ba0b-125">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="8ba0b-126">토큰 처리기가 인증서의 유효성을 검사하는 데 사용하는 설정을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba0b-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8ba0b-127">예제</span><span class="sxs-lookup"><span data-stu-id="8ba0b-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```

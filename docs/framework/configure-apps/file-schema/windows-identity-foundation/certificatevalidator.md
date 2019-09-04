---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 30f81dd5948a7d366c1116cffd347c85a396f5ae
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252121"
---
# <a name="certificatevalidator"></a><span data-ttu-id="fa40c-101">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="fa40c-101">\<certificateValidator></span></span>
<span data-ttu-id="fa40c-102">인증서 유효성 검사에 대 한 사용자 지정 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa40c-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="fa40c-103">이 형식은 `certificateValidationMode` [ \<certificatevalidation >](certificatevalidation.md) 요소의 특성이 "Custom"으로 설정 된 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa40c-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
<span data-ttu-id="fa40c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fa40c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fa40c-105">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="fa40c-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="fa40c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="fa40c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="fa40c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<certificateValidation >** ](certificatevalidation.md)</span><span class="sxs-lookup"><span data-stu-id="fa40c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)</span></span>\
<span data-ttu-id="fa40c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<certificateValidator >**</span><span class="sxs-lookup"><span data-stu-id="fa40c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa40c-109">구문</span><span class="sxs-lookup"><span data-stu-id="fa40c-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa40c-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fa40c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fa40c-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa40c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa40c-112">특성</span><span class="sxs-lookup"><span data-stu-id="fa40c-112">Attributes</span></span>  
  
|<span data-ttu-id="fa40c-113">특성</span><span class="sxs-lookup"><span data-stu-id="fa40c-113">Attribute</span></span>|<span data-ttu-id="fa40c-114">Description</span><span class="sxs-lookup"><span data-stu-id="fa40c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fa40c-115">type</span><span class="sxs-lookup"><span data-stu-id="fa40c-115">type</span></span>|<span data-ttu-id="fa40c-116"><xref:System.IdentityModel.Selectors.X509CertificateValidator> 클래스에서 파생 되는 사용자 지정 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa40c-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="fa40c-117">이 형식을 사용 하려면 [ \<certificatevalidation >](certificatevalidation.md) 요소의 특성을"Custom"으로설정합니다.`certificateValidationMode`</span><span class="sxs-lookup"><span data-stu-id="fa40c-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="fa40c-118">`type` 특성을 지정 하는 방법에 대 한 자세한 내용은 [사용자 지정 형식 참조](../windows-workflow-foundation/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa40c-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="fa40c-119">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fa40c-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa40c-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fa40c-120">Child Elements</span></span>  
 <span data-ttu-id="fa40c-121">없음</span><span class="sxs-lookup"><span data-stu-id="fa40c-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa40c-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fa40c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="fa40c-123">요소</span><span class="sxs-lookup"><span data-stu-id="fa40c-123">Element</span></span>|<span data-ttu-id="fa40c-124">설명</span><span class="sxs-lookup"><span data-stu-id="fa40c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa40c-125">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="fa40c-125">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="fa40c-126">토큰 처리기에서 인증서의 유효성을 검사 하는 데 사용 하는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa40c-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fa40c-127">예제</span><span class="sxs-lookup"><span data-stu-id="fa40c-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```

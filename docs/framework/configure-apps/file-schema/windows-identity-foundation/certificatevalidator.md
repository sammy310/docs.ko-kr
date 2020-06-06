---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 3f3d79d3567c1714a79423b7767ce3f454b9d52d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152790"
---
# \<certificateValidator>
<span data-ttu-id="bee4f-101">인증서 유효성 검사에 대 한 사용자 지정 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bee4f-101">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="bee4f-102">이 형식은 `certificateValidationMode` [\<certificateValidation>](certificatevalidation.md) 요소의 특성이 "Custom"으로 설정 된 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bee4f-102">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**  
  
## <a name="syntax"></a><span data-ttu-id="bee4f-103">구문</span><span class="sxs-lookup"><span data-stu-id="bee4f-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bee4f-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bee4f-104">Attributes and Elements</span></span>  
 <span data-ttu-id="bee4f-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bee4f-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bee4f-106">특성</span><span class="sxs-lookup"><span data-stu-id="bee4f-106">Attributes</span></span>  
  
|<span data-ttu-id="bee4f-107">attribute</span><span class="sxs-lookup"><span data-stu-id="bee4f-107">Attribute</span></span>|<span data-ttu-id="bee4f-108">Description</span><span class="sxs-lookup"><span data-stu-id="bee4f-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bee4f-109">type</span><span class="sxs-lookup"><span data-stu-id="bee4f-109">type</span></span>|<span data-ttu-id="bee4f-110">클래스에서 파생 되는 사용자 지정 형식을 지정 합니다 <xref:System.IdentityModel.Selectors.X509CertificateValidator> .</span><span class="sxs-lookup"><span data-stu-id="bee4f-110">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="bee4f-111">`certificateValidationMode` [\<certificateValidation>](certificatevalidation.md) 이 형식을 사용 하려면 요소의 특성을 "Custom"으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bee4f-111">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="bee4f-112">특성을 지정 하는 방법에 대 한 자세한 내용은 `type` [사용자 지정 형식 참조](../windows-workflow-foundation/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bee4f-112">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="bee4f-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bee4f-113">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bee4f-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bee4f-114">Child Elements</span></span>  
 <span data-ttu-id="bee4f-115">None</span><span class="sxs-lookup"><span data-stu-id="bee4f-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bee4f-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bee4f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="bee4f-117">요소</span><span class="sxs-lookup"><span data-stu-id="bee4f-117">Element</span></span>|<span data-ttu-id="bee4f-118">Description</span><span class="sxs-lookup"><span data-stu-id="bee4f-118">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="bee4f-119">토큰 처리기에서 인증서의 유효성을 검사 하는 데 사용 하는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="bee4f-119">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bee4f-120">예제</span><span class="sxs-lookup"><span data-stu-id="bee4f-120">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```

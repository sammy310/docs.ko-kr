---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: c25f183679f41f51ffee4f482bfe7a64763647d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941899"
---
# <a name="certificatevalidator"></a><span data-ttu-id="aa7a0-101">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="aa7a0-101">\<certificateValidator></span></span>
<span data-ttu-id="aa7a0-102">인증서 유효성 검사에 대 한 사용자 지정 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa7a0-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="aa7a0-103">이 형식은 `certificateValidationMode` [ \<certificatevalidation >](certificatevalidation.md) 요소의 특성이 "Custom"으로 설정 된 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa7a0-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="aa7a0-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="aa7a0-104">\<system.identityModel></span></span>  
<span data-ttu-id="aa7a0-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="aa7a0-105">\<identityConfiguration></span></span>  
<span data-ttu-id="aa7a0-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="aa7a0-106">\<certificateValidation></span></span>  
<span data-ttu-id="aa7a0-107">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="aa7a0-107">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa7a0-108">구문</span><span class="sxs-lookup"><span data-stu-id="aa7a0-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa7a0-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="aa7a0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="aa7a0-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aa7a0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa7a0-111">특성</span><span class="sxs-lookup"><span data-stu-id="aa7a0-111">Attributes</span></span>  
  
|<span data-ttu-id="aa7a0-112">특성</span><span class="sxs-lookup"><span data-stu-id="aa7a0-112">Attribute</span></span>|<span data-ttu-id="aa7a0-113">Description</span><span class="sxs-lookup"><span data-stu-id="aa7a0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa7a0-114">type</span><span class="sxs-lookup"><span data-stu-id="aa7a0-114">type</span></span>|<span data-ttu-id="aa7a0-115"><xref:System.IdentityModel.Selectors.X509CertificateValidator> 클래스에서 파생 되는 사용자 지정 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa7a0-115">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="aa7a0-116">이 형식을 사용 하려면 [ \<certificatevalidation >](certificatevalidation.md) 요소의 특성을"Custom"으로설정합니다.`certificateValidationMode`</span><span class="sxs-lookup"><span data-stu-id="aa7a0-116">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="aa7a0-117">`type` 특성을 지정 하는 방법에 대 한 자세한 내용은 [사용자 지정 형식 참조](../windows-workflow-foundation/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa7a0-117">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="aa7a0-118">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aa7a0-118">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa7a0-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="aa7a0-119">Child Elements</span></span>  
 <span data-ttu-id="aa7a0-120">없음</span><span class="sxs-lookup"><span data-stu-id="aa7a0-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aa7a0-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="aa7a0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="aa7a0-122">요소</span><span class="sxs-lookup"><span data-stu-id="aa7a0-122">Element</span></span>|<span data-ttu-id="aa7a0-123">Description</span><span class="sxs-lookup"><span data-stu-id="aa7a0-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa7a0-124">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="aa7a0-124">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="aa7a0-125">토큰 처리기에서 인증서의 유효성을 검사 하는 데 사용 하는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa7a0-125">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="aa7a0-126">예제</span><span class="sxs-lookup"><span data-stu-id="aa7a0-126">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```

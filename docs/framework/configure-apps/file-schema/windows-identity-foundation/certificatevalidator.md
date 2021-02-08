---
description: 다음에 대해 자세히 알아보세요. <certificateValidator>
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 0b92eada916b239ca56342021bb958da6d02c2e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802166"
---
# \<certificateValidator>

<span data-ttu-id="67812-102">인증서 유효성 검사에 대 한 사용자 지정 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="67812-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="67812-103">이 형식은 `certificateValidationMode` [\<certificateValidation>](certificatevalidation.md) 요소의 특성이 "Custom"으로 설정 된 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67812-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**  
  
## <a name="syntax"></a><span data-ttu-id="67812-104">구문</span><span class="sxs-lookup"><span data-stu-id="67812-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67812-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="67812-105">Attributes and Elements</span></span>  

 <span data-ttu-id="67812-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="67812-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67812-107">특성</span><span class="sxs-lookup"><span data-stu-id="67812-107">Attributes</span></span>  
  
|<span data-ttu-id="67812-108">attribute</span><span class="sxs-lookup"><span data-stu-id="67812-108">Attribute</span></span>|<span data-ttu-id="67812-109">Description</span><span class="sxs-lookup"><span data-stu-id="67812-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="67812-110">type</span><span class="sxs-lookup"><span data-stu-id="67812-110">type</span></span>|<span data-ttu-id="67812-111">클래스에서 파생 되는 사용자 지정 형식을 지정 합니다 <xref:System.IdentityModel.Selectors.X509CertificateValidator> .</span><span class="sxs-lookup"><span data-stu-id="67812-111">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="67812-112">`certificateValidationMode` [\<certificateValidation>](certificatevalidation.md) 이 형식을 사용 하려면 요소의 특성을 "Custom"으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="67812-112">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="67812-113">특성을 지정 하는 방법에 대 한 자세한 내용은 `type` [사용자 지정 형식 참조](../windows-workflow-foundation/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="67812-113">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="67812-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="67812-114">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67812-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="67812-115">Child Elements</span></span>  

 <span data-ttu-id="67812-116">없음</span><span class="sxs-lookup"><span data-stu-id="67812-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="67812-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="67812-117">Parent Elements</span></span>  
  
|<span data-ttu-id="67812-118">요소</span><span class="sxs-lookup"><span data-stu-id="67812-118">Element</span></span>|<span data-ttu-id="67812-119">설명</span><span class="sxs-lookup"><span data-stu-id="67812-119">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="67812-120">토큰 처리기에서 인증서의 유효성을 검사 하는 데 사용 하는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="67812-120">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="67812-121">예제</span><span class="sxs-lookup"><span data-stu-id="67812-121">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```

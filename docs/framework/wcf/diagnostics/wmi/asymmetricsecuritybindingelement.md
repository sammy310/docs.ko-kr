---
description: '자세히 알아보기: AsymmetricSecurityBindingElement'
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 25d0ac205491e9ce27c59d3a0670d1e4a3150e21
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757945"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="942d8-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="942d8-103">AsymmetricSecurityBindingElement</span></span>

<span data-ttu-id="942d8-104">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="942d8-104">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="942d8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="942d8-105">Syntax</span></span>  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="942d8-106">메서드</span><span class="sxs-lookup"><span data-stu-id="942d8-106">Methods</span></span>  

 <span data-ttu-id="942d8-107">AsymmetricSecurityBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="942d8-107">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="942d8-108">속성</span><span class="sxs-lookup"><span data-stu-id="942d8-108">Properties</span></span>  

 <span data-ttu-id="942d8-109">AsymmetricSecurityBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="942d8-109">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="942d8-110">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="942d8-110">MessageProtectionOrder</span></span>  

 <span data-ttu-id="942d8-111">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="942d8-111">Data type: string</span></span>  
  
 <span data-ttu-id="942d8-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="942d8-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="942d8-113">이 바인딩의 메시지 암호화 및 서명 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="942d8-113">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="942d8-114">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="942d8-114">RequireSignatureConfirmation</span></span>  

 <span data-ttu-id="942d8-115">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="942d8-115">Data type: boolean</span></span>  
  
 <span data-ttu-id="942d8-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="942d8-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="942d8-117">바인딩에 서명 확인이 필요한지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="942d8-117">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="942d8-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="942d8-118">Requirements</span></span>  
  
|<span data-ttu-id="942d8-119">MOF</span><span class="sxs-lookup"><span data-stu-id="942d8-119">MOF</span></span>|<span data-ttu-id="942d8-120">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="942d8-120">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="942d8-121">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="942d8-121">Namespace</span></span>|<span data-ttu-id="942d8-122">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="942d8-122">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="942d8-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="942d8-123">See also</span></span>

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

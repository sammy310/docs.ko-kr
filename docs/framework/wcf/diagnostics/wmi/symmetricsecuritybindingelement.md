---
description: '자세히 알아보기: SymmetricSecurityBindingElement'
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
ms.openlocfilehash: c158f0bedec91a74b305f359889dd307cff48079
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715303"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="f0aff-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f0aff-103">SymmetricSecurityBindingElement</span></span>

<span data-ttu-id="f0aff-104">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f0aff-104">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0aff-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0aff-105">Syntax</span></span>  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f0aff-106">메서드</span><span class="sxs-lookup"><span data-stu-id="f0aff-106">Methods</span></span>  

 <span data-ttu-id="f0aff-107">SymmetricSecurityBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0aff-107">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f0aff-108">속성</span><span class="sxs-lookup"><span data-stu-id="f0aff-108">Properties</span></span>  

 <span data-ttu-id="f0aff-109">SymmetricSecurityBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0aff-109">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="f0aff-110">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="f0aff-110">MessageProtectionOrder</span></span>  

 <span data-ttu-id="f0aff-111">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="f0aff-111">Data type: string</span></span>  
  
 <span data-ttu-id="f0aff-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="f0aff-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f0aff-113">이 바인딩의 메시지 암호화 및 서명 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="f0aff-113">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="f0aff-114">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="f0aff-114">RequireSignatureConfirmation</span></span>  

 <span data-ttu-id="f0aff-115">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="f0aff-115">Data type: boolean</span></span>  
  
 <span data-ttu-id="f0aff-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="f0aff-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f0aff-117">바인딩에 서명 확인이 필요한지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="f0aff-117">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0aff-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0aff-118">Requirements</span></span>  
  
|<span data-ttu-id="f0aff-119">MOF</span><span class="sxs-lookup"><span data-stu-id="f0aff-119">MOF</span></span>|<span data-ttu-id="f0aff-120">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0aff-120">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f0aff-121">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="f0aff-121">Namespace</span></span>|<span data-ttu-id="f0aff-122">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0aff-122">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0aff-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0aff-123">See also</span></span>

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

---
title: IDefinitionAppId 인터페이스
ms.date: 03/30/2017
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
ms.openlocfilehash: 5114f74e80da925c7a153b9e481c54067152eaec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108206"
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="1a584-102">IDefinitionAppId 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1a584-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="1a584-103">현재 범위에서 응용 프로그램을 정의 하는 코드의 고유 식별자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1a584-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1a584-104">메서드</span><span class="sxs-lookup"><span data-stu-id="1a584-104">Methods</span></span>  
  
|<span data-ttu-id="1a584-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1a584-105">Method</span></span>|<span data-ttu-id="1a584-106">설명</span><span class="sxs-lookup"><span data-stu-id="1a584-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="1a584-107">이 `IDefinitionAppId` 개체의 코드를 나타내는 형식이 지정 된 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1a584-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="1a584-108">이 `IDefinitionAppId` 개체의 코드를 지정 된 형식이 지정 된 문자열 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a584-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="1a584-109">현재 응용 프로그램 경로의 어셈블리를 포함 하는 [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1a584-109">Gets an interface pointer to an [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="1a584-110">현재 범위에 있는 어셈블리의 응용 프로그램 경로를 지정 된 [Idefinitionidentity](idefinitionidentity-interface.md) 개체에서 참조 하는 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a584-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="1a584-111">이 `IDefinitionAppId` 개체에 대 한 구독의 토큰 식별자에 대 한 문자열 표현에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1a584-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="1a584-112">이 `IDefinitionAppId` 개체에 대 한 구독의 토큰 식별자를 지정 된 문자열 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a584-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1a584-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1a584-113">Requirements</span></span>  
 <span data-ttu-id="1a584-114">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a584-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a584-115">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="1a584-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="1a584-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a584-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a584-117">참조</span><span class="sxs-lookup"><span data-stu-id="1a584-117">See also</span></span>

- [<span data-ttu-id="1a584-118">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1a584-118">Fusion Interfaces</span></span>](fusion-interfaces.md)

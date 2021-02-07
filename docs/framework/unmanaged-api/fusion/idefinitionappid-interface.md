---
description: '자세히 알아보기: IDefinitionAppId 인터페이스'
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
ms.openlocfilehash: 3c68044e7e747521e190fad404e89d6d0a994611
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760669"
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="e5952-103">IDefinitionAppId 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5952-103">IDefinitionAppId Interface</span></span>

<span data-ttu-id="e5952-104">현재 범위에서 응용 프로그램을 정의 하는 코드의 고유 식별자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5952-104">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5952-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e5952-105">Methods</span></span>  
  
|<span data-ttu-id="e5952-106">메서드</span><span class="sxs-lookup"><span data-stu-id="e5952-106">Method</span></span>|<span data-ttu-id="e5952-107">설명</span><span class="sxs-lookup"><span data-stu-id="e5952-107">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="e5952-108">이 개체의 코드를 나타내는 형식이 지정 된 문자열을 가져옵니다 `IDefinitionAppId` .</span><span class="sxs-lookup"><span data-stu-id="e5952-108">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="e5952-109">이 개체의 코드를 `IDefinitionAppId` 지정 된 형식이 지정 된 문자열 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5952-109">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="e5952-110">현재 응용 프로그램 경로의 어셈블리를 포함 하는 [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e5952-110">Gets an interface pointer to an [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="e5952-111">현재 범위에 있는 어셈블리의 응용 프로그램 경로를 지정 된 [Idefinitionidentity](idefinitionidentity-interface.md) 개체에서 참조 하는 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5952-111">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="e5952-112">이 개체에 대 한 구독의 토큰 식별자에 대 한 문자열 표현에 대 한 포인터를 가져옵니다 `IDefinitionAppId` .</span><span class="sxs-lookup"><span data-stu-id="e5952-112">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="e5952-113">이 개체에 대 한 구독의 토큰 식별자를 `IDefinitionAppId` 지정 된 문자열 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5952-113">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e5952-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5952-114">Requirements</span></span>  

 <span data-ttu-id="e5952-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5952-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5952-116">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="e5952-116">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="e5952-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5952-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5952-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5952-118">See also</span></span>

- [<span data-ttu-id="e5952-119">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5952-119">Fusion Interfaces</span></span>](fusion-interfaces.md)

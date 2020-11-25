---
title: IDefinitionIdentity 인터페이스
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
ms.openlocfilehash: 4f08fbbf9c8be16dff092327713e731c5aa14661
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732879"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="9500d-102">IDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9500d-102">IDefinitionIdentity Interface</span></span>

<span data-ttu-id="9500d-103">현재 범위에서 응용 프로그램을 정의 하는 코드의 고유 서명을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9500d-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9500d-104">메서드</span><span class="sxs-lookup"><span data-stu-id="9500d-104">Methods</span></span>  
  
|<span data-ttu-id="9500d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9500d-105">Method</span></span>|<span data-ttu-id="9500d-106">설명</span><span class="sxs-lookup"><span data-stu-id="9500d-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="9500d-107">지정 된 특성이 변경 되는 경우를 제외 하 고이와 동일한 새 개체에 대 한 인터페이스 포인터를 가져옵니다 `IDefinitionIdentity` `IDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="9500d-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="9500d-108">이와 연결 된 특성을 포함 하는 [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) 개체에 대 한 인터페이스 포인터를 가져옵니다 `IDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="9500d-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="9500d-109">지정 된 네임 스페이스에서 지정 된 이름을 가진 특성의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9500d-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="9500d-110">지정 된 네임 스페이스에서 지정 된 이름을 가진 특성을 지정 된 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9500d-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9500d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9500d-111">Requirements</span></span>  

 <span data-ttu-id="9500d-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9500d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9500d-113">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="9500d-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="9500d-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9500d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9500d-115">참조</span><span class="sxs-lookup"><span data-stu-id="9500d-115">See also</span></span>

- [<span data-ttu-id="9500d-116">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9500d-116">Fusion Interfaces</span></span>](fusion-interfaces.md)

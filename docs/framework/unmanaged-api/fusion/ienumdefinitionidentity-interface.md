---
title: IEnumDefinitionIdentity 인터페이스
ms.date: 03/30/2017
api_name:
- IEnumDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumDefinitionIdentity
helpviewer_keywords:
- IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type:
- apiref
ms.openlocfilehash: 09c6431ec885c8b797dc9bb5f5c3ffe21890ccc7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107947"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="a3fef-102">IEnumDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a3fef-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="a3fef-103">`IDefinitionIdentity` 개체의 컬렉션에 대 한 열거자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fef-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3fef-104">구문</span><span class="sxs-lookup"><span data-stu-id="a3fef-104">Syntax</span></span>  
  
```cpp  
IEnumDefinitionIdentity : IUnknown {  
  
    HRESULT Clone (  
        [out] IEnumDefinitionIdentity **ppIEnumDefinitionIdentity  
    );  
  
    HRESULT Next (  
        [in]  ULONG               celt,  
        [out, length_is(celt), size_is(*pceltWritten)]  
              IDefinitionIdentity *rgpIDefinitionIdentity[],  
        [out] ULONG               *pceltWritten  
    );  
  
    HRESULT Reset ();  
  
    HRESULT Skip (  
        [in] ULONG celt  
    );  
  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a3fef-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a3fef-105">Methods</span></span>  
  
|<span data-ttu-id="a3fef-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a3fef-106">Method</span></span>|<span data-ttu-id="a3fef-107">설명</span><span class="sxs-lookup"><span data-stu-id="a3fef-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="a3fef-108">이 `IEnumDefinitionIdentity`와 동일한 멤버를 포함 하는 새 `IEnumDefinitionIdentity` 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a3fef-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="a3fef-109">현재 위치에서 시작 하 여 지정 된 수의 `IDefinitionIdentity` 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a3fef-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="a3fef-110">명령 포인터를이 `IEnumDefinitionIdentity`의 시작 부분으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fef-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="a3fef-111">명령 포인터를 현재 위치에서 시작 하 여 지정 된 요소 수 만큼 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fef-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a3fef-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a3fef-112">Requirements</span></span>  
 <span data-ttu-id="a3fef-113">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3fef-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3fef-114">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="a3fef-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="a3fef-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3fef-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3fef-116">참조</span><span class="sxs-lookup"><span data-stu-id="a3fef-116">See also</span></span>

- [<span data-ttu-id="a3fef-117">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a3fef-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="a3fef-118">IDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a3fef-118">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)

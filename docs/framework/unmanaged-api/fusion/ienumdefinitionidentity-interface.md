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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bbd8476b7778de6d0023f3a8522a44be6626884
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751519"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="5000d-102">IEnumDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5000d-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="5000d-103">컬렉션의 열거자 역할을 `IDefinitionIdentity` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5000d-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5000d-104">구문</span><span class="sxs-lookup"><span data-stu-id="5000d-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="5000d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5000d-105">Methods</span></span>  
  
|<span data-ttu-id="5000d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="5000d-106">Method</span></span>|<span data-ttu-id="5000d-107">Description</span><span class="sxs-lookup"><span data-stu-id="5000d-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="5000d-108">새 인터페이스 포인터를 가져옵니다 `IEnumDefinitionIdentity` 이 동일한 멤버를 포함 하는 개체 `IEnumDefinitionIdentity`합니다.</span><span class="sxs-lookup"><span data-stu-id="5000d-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="5000d-109">지정 된 수를 가져옵니다 `IDefinitionIdentity` 개체를 현재 위치에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5000d-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="5000d-110">이 부분에 명령 포인터를 이동 `IEnumDefinitionIdentity`합니다.</span><span class="sxs-lookup"><span data-stu-id="5000d-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="5000d-111">요소를 현재 위치부터 지정한 수 만큼 앞으로 명령 포인터를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5000d-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5000d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5000d-112">Requirements</span></span>  
 <span data-ttu-id="5000d-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5000d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5000d-114">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="5000d-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="5000d-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5000d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5000d-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="5000d-116">See also</span></span>

- [<span data-ttu-id="5000d-117">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5000d-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="5000d-118">IDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5000d-118">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)

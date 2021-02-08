---
description: '자세히 알아보기: IEnumDefinitionIdentity 인터페이스'
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
ms.openlocfilehash: 1055031c064115410334bbe4b20b48deee7ec4c4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800164"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="ce066-103">IEnumDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce066-103">IEnumDefinitionIdentity Interface</span></span>

<span data-ttu-id="ce066-104">개체의 컬렉션에 대 한 열거자 역할을 `IDefinitionIdentity` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce066-104">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce066-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce066-105">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="ce066-106">메서드</span><span class="sxs-lookup"><span data-stu-id="ce066-106">Methods</span></span>  
  
|<span data-ttu-id="ce066-107">메서드</span><span class="sxs-lookup"><span data-stu-id="ce066-107">Method</span></span>|<span data-ttu-id="ce066-108">설명</span><span class="sxs-lookup"><span data-stu-id="ce066-108">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="ce066-109">`IEnumDefinitionIdentity`이와 동일한 멤버를 포함 하는 새 개체에 대 한 인터페이스 포인터를 가져옵니다 `IEnumDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="ce066-109">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="ce066-110">현재 위치에서 시작 하 여 지정 된 수의 `IDefinitionIdentity` 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ce066-110">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="ce066-111">명령 포인터를이의 시작 부분으로 이동 합니다 `IEnumDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="ce066-111">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="ce066-112">명령 포인터를 현재 위치에서 시작 하 여 지정 된 요소 수 만큼 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce066-112">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ce066-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce066-113">Requirements</span></span>  

 <span data-ttu-id="ce066-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce066-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce066-115">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="ce066-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="ce066-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce066-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce066-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce066-117">See also</span></span>

- [<span data-ttu-id="ce066-118">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce066-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="ce066-119">IDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce066-119">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)

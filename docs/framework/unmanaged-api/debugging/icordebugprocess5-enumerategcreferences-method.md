---
description: '자세히 알아보기: ICorDebugProcess5:: EnumerateGCReferences 메서드'
title: ICorDebugProcess5::EnumerateGCReferences 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
ms.openlocfilehash: 5145fd072b083ed107b874fe99403984915233ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746414"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="dcf1f-103">ICorDebugProcess5::EnumerateGCReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="dcf1f-103">ICorDebugProcess5::EnumerateGCReferences Method</span></span>

<span data-ttu-id="dcf1f-104">프로세스에서 가비지 수집 될 모든 개체에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-104">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcf1f-105">구문</span><span class="sxs-lookup"><span data-stu-id="dcf1f-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcf1f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dcf1f-106">Parameters</span></span>  

 `enumerateWeakReferences`  
 <span data-ttu-id="dcf1f-107">진행 약한 참조도 열거 되는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-107">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="dcf1f-108">`enumerateWeakReferences`가 이면 `true` 열거자에는 `ppEnum` 강력한 참조와 weak 참조가 모두 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-108">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="dcf1f-109">`enumerateWeakReferences`가 이면 `false` 열거자에는 강력한 참조만 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-109">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="dcf1f-110">제한이 가비지 수집 될 개체의 열거자 인 [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) 의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-110">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcf1f-111">설명</span><span class="sxs-lookup"><span data-stu-id="dcf1f-111">Remarks</span></span>  

 <span data-ttu-id="dcf1f-112">이 메서드는 프로세스에서 관리 되는 개체에 대 한 전체 루 팅 체인을 확인 하는 방법을 제공 하 고 개체의 활성 상태를 확인 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-112">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcf1f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dcf1f-113">Requirements</span></span>  

 <span data-ttu-id="dcf1f-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcf1f-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dcf1f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcf1f-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcf1f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcf1f-117">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcf1f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcf1f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dcf1f-118">See also</span></span>

- [<span data-ttu-id="dcf1f-119">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dcf1f-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="dcf1f-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dcf1f-120">Debugging Interfaces</span></span>](debugging-interfaces.md)

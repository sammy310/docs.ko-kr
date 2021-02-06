---
description: '자세히 알아보기: ICorDebugProcess5:: EnumerateHandles 메서드'
title: ICorDebugProcess5::EnumerateHandles 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
ms.openlocfilehash: 62ca1390ceec634e6651dc013345688fe5892bcd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649912"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="c34f0-103">ICorDebugProcess5::EnumerateHandles 메서드</span><span class="sxs-lookup"><span data-stu-id="c34f0-103">ICorDebugProcess5::EnumerateHandles Method</span></span>

<span data-ttu-id="c34f0-104">프로세스의 개체 핸들에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c34f0-104">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c34f0-105">구문</span><span class="sxs-lookup"><span data-stu-id="c34f0-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c34f0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c34f0-106">Parameters</span></span>  

 `types`  
 <span data-ttu-id="c34f0-107">진행 컬렉션에 포함할 핸들의 형식을 지정 하는 [CorGCReferenceType](corgcreferencetype-enumeration.md) 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="c34f0-107">[in] A bitwise combination of [CorGCReferenceType](corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="c34f0-108">제한이 가비지 수집 될 개체의 열거자 인 [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) 의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c34f0-108">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c34f0-109">설명</span><span class="sxs-lookup"><span data-stu-id="c34f0-109">Remarks</span></span>  

 <span data-ttu-id="c34f0-110">`EnumerateHandles` 는 핸들 테이블의 검사를 지 원하는 도우미 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c34f0-110">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="c34f0-111">[ICorDebugProcess5:: EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) 메서드와 유사 합니다. 단, 가비지 수집 되는 모든 개체를 사용 하 여 [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) 컬렉션을 채우지 않고 핸들 테이블의 핸들을 포함 하는 개체만 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c34f0-111">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="c34f0-112">`types`매개 변수는 컬렉션에 포함할 핸들 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c34f0-112">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="c34f0-113">`types`[CorGCReferenceType](corgcreferencetype-enumeration.md) 열거형의 다음 세 가지 멤버 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c34f0-113">`types` can be any of the following three members of the [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
- <span data-ttu-id="c34f0-114">`CorHandleStrongOnly` (강력한 참조에만 해당).</span><span class="sxs-lookup"><span data-stu-id="c34f0-114">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
- <span data-ttu-id="c34f0-115">`CorHandleWeakOnly` (약한 참조에만 해당).</span><span class="sxs-lookup"><span data-stu-id="c34f0-115">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
- <span data-ttu-id="c34f0-116">`CorHandleAll` (모든 핸들).</span><span class="sxs-lookup"><span data-stu-id="c34f0-116">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c34f0-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c34f0-117">Requirements</span></span>  

 <span data-ttu-id="c34f0-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c34f0-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c34f0-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c34f0-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c34f0-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c34f0-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c34f0-121">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c34f0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c34f0-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c34f0-122">See also</span></span>

- [<span data-ttu-id="c34f0-123">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="c34f0-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="c34f0-124">디버깅</span><span class="sxs-lookup"><span data-stu-id="c34f0-124">Debugging</span></span>](index.md)

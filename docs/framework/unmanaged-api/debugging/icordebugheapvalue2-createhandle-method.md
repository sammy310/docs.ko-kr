---
description: '자세히 알아보기: ICorDebugHeapValue2:: CreateHandle 메서드'
title: ICorDebugHeapValue2::CreateHandle 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2.CreateHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type:
- apiref
ms.openlocfilehash: d93fee71441b9c510d517acb9582b8d1d9ce9e10
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803661"
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="c9784-103">ICorDebugHeapValue2::CreateHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="c9784-103">ICorDebugHeapValue2::CreateHandle Method</span></span>

<span data-ttu-id="c9784-104">이 ICorDebugHeapValue2 개체가 나타내는 힙 값에 대해 지정 된 형식의 핸들을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9784-104">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9784-105">구문</span><span class="sxs-lookup"><span data-stu-id="c9784-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9784-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c9784-106">Parameters</span></span>  

 `type`  
 <span data-ttu-id="c9784-107">진행 만들 핸들의 유형을 지정 하는 CorDebugHandleType 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c9784-107">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="c9784-108">제한이 이 힙 값의 새 핸들을 나타내는 ICorDebugHandleValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c9784-108">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9784-109">설명</span><span class="sxs-lookup"><span data-stu-id="c9784-109">Remarks</span></span>  

 <span data-ttu-id="c9784-110">이 핸들은 힙 값과 연결 된 응용 프로그램 도메인에 생성 되며 응용 프로그램 도메인이 언로드될 경우 유효 하지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9784-110">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="c9784-111">동일한 힙 값에 대해이 함수를 여러 번 호출 하면 여러 개의 핸들이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9784-111">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="c9784-112">핸들이 가비지 수집기의 성능에 영향을 주므로 디버거는 한 번에 활성 상태인 상대적으로 적은 수의 핸들 (약 256)으로 제한 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9784-112">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9784-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c9784-113">Requirements</span></span>  

 <span data-ttu-id="c9784-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9784-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9784-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9784-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9784-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9784-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9784-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9784-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

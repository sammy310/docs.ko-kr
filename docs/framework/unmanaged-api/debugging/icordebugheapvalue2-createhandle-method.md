---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 078dfd7162c250f0279b8bc372aeb39662aa0119
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779888"
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="c404a-102">ICorDebugHeapValue2::CreateHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="c404a-102">ICorDebugHeapValue2::CreateHandle Method</span></span>
<span data-ttu-id="c404a-103">이 ICorDebugHeapValue2 개체로 표현 되는 힙 값에 대 한 지정 된 형식의 핸들을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c404a-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c404a-104">구문</span><span class="sxs-lookup"><span data-stu-id="c404a-104">Syntax</span></span>  
  
```  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c404a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c404a-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="c404a-106">[in] 만들려는 핸들의 형식을 지정 하는 CorDebugHandleType 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c404a-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="c404a-107">[out] 이 힙 값에 대 한 새 핸들을 나타내는 ICorDebugHandleValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c404a-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c404a-108">설명</span><span class="sxs-lookup"><span data-stu-id="c404a-108">Remarks</span></span>  
 <span data-ttu-id="c404a-109">핸들 힙 값을 사용 하 여 연결 된 응용 프로그램 도메인에서 만들어지고 응용 프로그램 도메인이 언로드된 경우 유효 하지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c404a-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="c404a-110">같은 힙 값에 대 한이 함수를 여러 번 호출을 여러 핸들을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c404a-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="c404a-111">가비지 수집의 성능에 영향을 주는 처리 하기 때문에 디버거에서 상대적으로 적은 수의 한 번에 활성 상태인 처리 (약 256) 자체를 제한 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c404a-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c404a-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c404a-112">Requirements</span></span>  
 <span data-ttu-id="c404a-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c404a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c404a-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c404a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c404a-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c404a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c404a-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c404a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

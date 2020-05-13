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
ms.openlocfilehash: cbc056e9a3cc00178b32dee4011da4403dff508a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212778"
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="b08e9-102">ICorDebugHeapValue2::CreateHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="b08e9-102">ICorDebugHeapValue2::CreateHandle Method</span></span>
<span data-ttu-id="b08e9-103">이 ICorDebugHeapValue2 개체가 나타내는 힙 값에 대해 지정 된 형식의 핸들을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b08e9-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b08e9-104">구문</span><span class="sxs-lookup"><span data-stu-id="b08e9-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b08e9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b08e9-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="b08e9-106">진행 만들 핸들의 유형을 지정 하는 CorDebugHandleType 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b08e9-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="b08e9-107">제한이 이 힙 값의 새 핸들을 나타내는 ICorDebugHandleValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b08e9-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b08e9-108">설명</span><span class="sxs-lookup"><span data-stu-id="b08e9-108">Remarks</span></span>  
 <span data-ttu-id="b08e9-109">이 핸들은 힙 값과 연결 된 응용 프로그램 도메인에 생성 되며 응용 프로그램 도메인이 언로드될 경우 유효 하지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b08e9-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="b08e9-110">동일한 힙 값에 대해이 함수를 여러 번 호출 하면 여러 개의 핸들이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b08e9-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="b08e9-111">핸들이 가비지 수집기의 성능에 영향을 주므로 디버거는 한 번에 활성 상태인 상대적으로 적은 수의 핸들 (약 256)으로 제한 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b08e9-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b08e9-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b08e9-112">Requirements</span></span>  
 <span data-ttu-id="b08e9-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b08e9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b08e9-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b08e9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b08e9-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b08e9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b08e9-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b08e9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

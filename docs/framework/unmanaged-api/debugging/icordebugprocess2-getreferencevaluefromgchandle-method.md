---
title: ICorDebugProcess2::GetReferenceValueFromGCHandle 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type:
- apiref
ms.openlocfilehash: 47647bf0460507b4c88b47bf87bfcc3bf620aecc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137216"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="f5677-102">ICorDebugProcess2::GetReferenceValueFromGCHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="f5677-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>
<span data-ttu-id="f5677-103">가비지 수집 핸들이 있는 지정 된 관리 되는 개체에 대 한 참조 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f5677-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5677-104">구문</span><span class="sxs-lookup"><span data-stu-id="f5677-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5677-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f5677-105">Parameters</span></span>  
 `handle`  
 <span data-ttu-id="f5677-106">진행 가비지 수집 핸들이 있는 관리 되는 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f5677-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="f5677-107">이 값은 <xref:System.IntPtr> 개체 이며 관리 되는 개체에 대 한 <xref:System.Runtime.InteropServices.GCHandle>에서 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5677-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="f5677-108">제한이 지정 된 관리 되는 개체에 대 한 참조를 나타내는 ICorDebugReferenceValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f5677-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5677-109">주의</span><span class="sxs-lookup"><span data-stu-id="f5677-109">Remarks</span></span>  
 <span data-ttu-id="f5677-110">반환 된 참조 값과 가비지 수집 참조 값을 혼동 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="f5677-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="f5677-111">반환 된 참조는 일반 참조 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5677-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="f5677-112">중단점 후 코드 실행이 계속 되 면 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5677-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="f5677-113">대상 개체의 수명은 참조 값의 수명에 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5677-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f5677-114">`GetReferenceValueFromGCHandle` 메서드는 핸들의 유효성을 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5677-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="f5677-115">따라서 `GetReferenceValueFromGCHandle` 메서드는 잘못 된 핸들이 전달 될 경우 디버거 및 디버깅 중인 코드를 모두 손상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5677-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5677-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f5677-116">Requirements</span></span>  
 <span data-ttu-id="f5677-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5677-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5677-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5677-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5677-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5677-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5677-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5677-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

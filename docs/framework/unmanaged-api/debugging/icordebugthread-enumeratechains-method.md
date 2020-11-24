---
title: ICorDebugThread::EnumerateChains 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.EnumerateChains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type:
- apiref
ms.openlocfilehash: 76b231f00651186518d3bccfafa5780f258c4f75
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688187"
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="7d733-102">ICorDebugThread::EnumerateChains 메서드</span><span class="sxs-lookup"><span data-stu-id="7d733-102">ICorDebugThread::EnumerateChains Method</span></span>

<span data-ttu-id="7d733-103">이 ICorDebugThread 개체의 모든 스택 체인을 포함 하는 ICorDebugChainEnum 열거자에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7d733-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d733-104">구문</span><span class="sxs-lookup"><span data-stu-id="7d733-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d733-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7d733-105">Parameters</span></span>  

 `ppChains`  
 <span data-ttu-id="7d733-106">제한이 `ICorDebugChainEnum` 활성 (가장 최근) 체인에서 시작 하 여이 스레드에서 모든 스택 체인을 열거할 수 있도록 하는 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7d733-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d733-107">설명</span><span class="sxs-lookup"><span data-stu-id="7d733-107">Remarks</span></span>  

 <span data-ttu-id="7d733-108">스택 체인은 스레드의 물리적 호출 스택을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d733-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="7d733-109">다음 상황에서는 스택 체인 경계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d733-109">The following circumstances create a stack chain boundary:</span></span>  
  
- <span data-ttu-id="7d733-110">관리 되는 관리 또는 관리 되지 않는 전환입니다.</span><span class="sxs-lookup"><span data-stu-id="7d733-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
- <span data-ttu-id="7d733-111">컨텍스트 전환.</span><span class="sxs-lookup"><span data-stu-id="7d733-111">A context switch.</span></span>  
  
- <span data-ttu-id="7d733-112">디버거는 사용자 스레드를 하이재킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d733-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="7d733-113">단일 컨텍스트에서 순수 하 게 관리 되는 코드를 실행 하는 스레드에 대 한 간단한 경우에는 스레드 및 스택 체인 사이에 일 대 일 대응이 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d733-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="7d733-114">디버거는 모든 스레드의 실제 호출 스택을 논리적 호출 스택으로 다시 정렬 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d733-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="7d733-115">여기에는 호출자/호출 수신자 관계로 모든 스레드 체인을 정렬 하 고 regrouping 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d733-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d733-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d733-116">Requirements</span></span>  

 <span data-ttu-id="7d733-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d733-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d733-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d733-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d733-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d733-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d733-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d733-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

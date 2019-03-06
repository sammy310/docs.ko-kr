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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e01f94e9574ebc032bc45490fd88ff92e9104aa3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482862"
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="5929c-102">ICorDebugThread::EnumerateChains 메서드</span><span class="sxs-lookup"><span data-stu-id="5929c-102">ICorDebugThread::EnumerateChains Method</span></span>
<span data-ttu-id="5929c-103">이 ICorDebugThread 개체의 모든 스택 체인을 포함 하는 ICorDebugChainEnum 열거자에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5929c-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5929c-104">구문</span><span class="sxs-lookup"><span data-stu-id="5929c-104">Syntax</span></span>  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5929c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5929c-105">Parameters</span></span>  
 `ppChains`  
 <span data-ttu-id="5929c-106">[out] 주소에 대 한 포인터는 `ICorDebugChainEnum` 활성 (즉, 가장 최근) 체인에서 시작,이 스레드의 모든 스택 열거를 사용할 수 있는 개체 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="5929c-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5929c-107">설명</span><span class="sxs-lookup"><span data-stu-id="5929c-107">Remarks</span></span>  
 <span data-ttu-id="5929c-108">스택 체인 스레드의 실제 호출 스택을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5929c-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="5929c-109">다음과 같은 경우 스택 체인 경계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5929c-109">The following circumstances create a stack chain boundary:</span></span>  
  
-   <span data-ttu-id="5929c-110">관리-비관리 또는 관리 되지 않는 관리로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5929c-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
-   <span data-ttu-id="5929c-111">컨텍스트 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5929c-111">A context switch.</span></span>  
  
-   <span data-ttu-id="5929c-112">사용자 스레드의 하이재킹 디버거.</span><span class="sxs-lookup"><span data-stu-id="5929c-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="5929c-113">단일 컨텍스트에 순수 관리 코드를 실행 하는 스레드에 대 한 간단한 경우 스레드 스택 체인 간의 일대일로 대응 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="5929c-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="5929c-114">디버거 논리 호출 스택을에 모든 스레드의 실제 호출 스택을 다시 정렬 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5929c-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="5929c-115">여기에 모든 스레드의 체인이 해당 호출자/호출 수신자 관계에 의해 정렬 되 고 이러한 다시 그룹화 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5929c-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5929c-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5929c-116">Requirements</span></span>  
 <span data-ttu-id="5929c-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5929c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5929c-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5929c-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5929c-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5929c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5929c-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5929c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

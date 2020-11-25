---
title: ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
ms.openlocfilehash: 779b737da43f61d1023a0a640dce936e11c4704c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707037"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="9d89c-102">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d89c-102">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>

<span data-ttu-id="9d89c-103">각 메서드 기호에 대 한 선택적 비동기 메서드 정보를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d89c-103">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="9d89c-104">항상 열린 메서드와 함께를 사용 합니다. 즉, [Openmethod 메서드와](isymunmanagedwriter-openmethod-method.md) [closemethod 메서드](isymunmanagedwriter-closemethod-method.md)를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d89c-104">Always use with an opened method; that is, between calls to the [OpenMethod Method](isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d89c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d89c-105">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="9d89c-106">메서드</span><span class="sxs-lookup"><span data-stu-id="9d89c-106">Methods</span></span>  

 <span data-ttu-id="9d89c-107">이 인터페이스에는 다음과 같은 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d89c-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="9d89c-108">메서드</span><span class="sxs-lookup"><span data-stu-id="9d89c-108">Method</span></span>|<span data-ttu-id="9d89c-109">설명</span><span class="sxs-lookup"><span data-stu-id="9d89c-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d89c-110">DefineAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="9d89c-110">DefineAsyncStepInfo Method</span></span>](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="9d89c-111">현재 메서드에서 비동기 대기 작업 그룹을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d89c-111">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="9d89c-112">각 양보 오프셋은 대기의 반환 명령과 일치 하므로 잠재적 양보를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d89c-112">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="9d89c-113">각 `breakpointMethod` / `breakpointOffset` 쌍은 비동기 작업이 다시 시작 되는 위치를 식별 합니다. 다른 메서드에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d89c-113">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="9d89c-114">DefineCatchHandlerILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="9d89c-114">DefineCatchHandlerILOffset Method</span></span>](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="9d89c-115">비동기 메서드를 래핑하는 컴파일러 생성 catch 처리기에 대 한 IL 오프셋을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d89c-115">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="9d89c-116">생성 된 catch의 IL 오프셋은 디버거에서 사용자 코드 메서드에서 발생할 수 있는 경우에도 사용자가 작성 하지 않은 코드 였던 것 처럼 catch를 처리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d89c-116">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="9d89c-117">특히 **CatchHandlerFound** exception 이벤트에 대 한 응답에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d89c-117">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="9d89c-118">DefineKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="9d89c-118">DefineKickoffMethod Method</span></span>](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="9d89c-119">비동기 작업을 시작 하는 시작 메서드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d89c-119">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9d89c-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9d89c-120">Requirements</span></span>  

 <span data-ttu-id="9d89c-121">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="9d89c-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d89c-122">참조</span><span class="sxs-lookup"><span data-stu-id="9d89c-122">See also</span></span>

- [<span data-ttu-id="9d89c-123">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d89c-123">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)

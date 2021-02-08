---
description: '자세히 알아보기: ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스'
title: ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
ms.openlocfilehash: 4c8b1bc037485e22160af28b59d751859a157499
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790193"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="473d5-103">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="473d5-103">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>

<span data-ttu-id="473d5-104">각 메서드 기호에 대 한 선택적 비동기 메서드 정보를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="473d5-104">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="473d5-105">항상 열린 메서드와 함께를 사용 합니다. 즉, [Openmethod 메서드와](isymunmanagedwriter-openmethod-method.md) [closemethod 메서드](isymunmanagedwriter-closemethod-method.md)를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="473d5-105">Always use with an opened method; that is, between calls to the [OpenMethod Method](isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="473d5-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="473d5-106">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="473d5-107">메서드</span><span class="sxs-lookup"><span data-stu-id="473d5-107">Methods</span></span>  

 <span data-ttu-id="473d5-108">이 인터페이스에는 다음과 같은 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="473d5-108">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="473d5-109">메서드</span><span class="sxs-lookup"><span data-stu-id="473d5-109">Method</span></span>|<span data-ttu-id="473d5-110">설명</span><span class="sxs-lookup"><span data-stu-id="473d5-110">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="473d5-111">DefineAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="473d5-111">DefineAsyncStepInfo Method</span></span>](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="473d5-112">현재 메서드에서 비동기 대기 작업 그룹을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="473d5-112">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="473d5-113">각 양보 오프셋은 대기의 반환 명령과 일치 하므로 잠재적 양보를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="473d5-113">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="473d5-114">각 `breakpointMethod` / `breakpointOffset` 쌍은 비동기 작업이 다시 시작 되는 위치를 식별 합니다. 다른 메서드에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="473d5-114">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="473d5-115">DefineCatchHandlerILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="473d5-115">DefineCatchHandlerILOffset Method</span></span>](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="473d5-116">비동기 메서드를 래핑하는 컴파일러 생성 catch 처리기에 대 한 IL 오프셋을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="473d5-116">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="473d5-117">생성 된 catch의 IL 오프셋은 디버거에서 사용자 코드 메서드에서 발생할 수 있는 경우에도 사용자가 작성 하지 않은 코드 였던 것 처럼 catch를 처리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="473d5-117">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="473d5-118">특히 **CatchHandlerFound** exception 이벤트에 대 한 응답에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="473d5-118">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="473d5-119">DefineKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="473d5-119">DefineKickoffMethod Method</span></span>](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="473d5-120">비동기 작업을 시작 하는 시작 메서드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="473d5-120">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="473d5-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="473d5-121">Requirements</span></span>  

 <span data-ttu-id="473d5-122">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="473d5-122">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="473d5-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="473d5-123">See also</span></span>

- [<span data-ttu-id="473d5-124">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="473d5-124">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)

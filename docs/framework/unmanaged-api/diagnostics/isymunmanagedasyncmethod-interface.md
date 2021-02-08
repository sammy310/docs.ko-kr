---
description: '자세히 알아보기: ISymUnmanagedAsyncMethod 인터페이스'
title: ISymUnmanagedAsyncMethod 인터페이스
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: cb3120464224137dfdcff4f13ca4aee82ef4d89e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790271"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="3e692-103">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e692-103">ISymUnmanagedAsyncMethod Interface</span></span>

<span data-ttu-id="3e692-104">이 인터페이스는 [ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스](isymunmanagedasyncmethodpropertieswriter-interface.md)에 대 한 읽기 보수입니다.</span><span class="sxs-lookup"><span data-stu-id="3e692-104">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e692-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e692-105">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="3e692-106">메서드</span><span class="sxs-lookup"><span data-stu-id="3e692-106">Methods</span></span>  

 <span data-ttu-id="3e692-107">이 인터페이스에는 다음과 같은 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e692-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="3e692-108">메서드</span><span class="sxs-lookup"><span data-stu-id="3e692-108">Method</span></span>|<span data-ttu-id="3e692-109">설명</span><span class="sxs-lookup"><span data-stu-id="3e692-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3e692-110">GetAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="3e692-110">GetAsyncStepInfo Method</span></span>](isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="3e692-111">[DefineAsyncStepInfo 메서드](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e692-111">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="3e692-112">GetAsyncStepInfoCount 메서드</span><span class="sxs-lookup"><span data-stu-id="3e692-112">GetAsyncStepInfoCount Method</span></span>](isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="3e692-113">[DefineAsyncStepInfo 메서드](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e692-113">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="3e692-114">GetCatchHandlerILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="3e692-114">GetCatchHandlerILOffset Method</span></span>](isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="3e692-115">정의 [Ecatchhandleriloffset 메서드](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e692-115">See [DefineCatchHandlerILOffset Method](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="3e692-116">GetKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="3e692-116">GetKickoffMethod Method</span></span>](isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="3e692-117">[DefineKickoffMethod 메서드](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e692-117">See [DefineKickoffMethod Method](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="3e692-118">HasCatchHandlerILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="3e692-118">HasCatchHandlerILOffset Method</span></span>](isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="3e692-119">정의 [Ecatchhandleriloffset 메서드](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e692-119">See [DefineCatchHandlerILOffset Method](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="3e692-120">IsAsyncMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="3e692-120">IsAsyncMethod Method</span></span>](isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="3e692-121">메서드에 비동기 정보가 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e692-121">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="3e692-122">이 메서드가를 반환 `FALSE` 하는 경우이 인터페이스에서 다른 메서드를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e692-122">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="3e692-123">이 경우 모두 반환 됩니다 `E_UNEXPECTED` .</span><span class="sxs-lookup"><span data-stu-id="3e692-123">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3e692-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e692-124">Requirements</span></span>  

 <span data-ttu-id="3e692-125">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="3e692-125">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e692-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e692-126">See also</span></span>

- [<span data-ttu-id="3e692-127">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e692-127">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)

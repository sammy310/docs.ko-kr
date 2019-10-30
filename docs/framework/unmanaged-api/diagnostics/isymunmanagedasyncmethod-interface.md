---
title: ISymUnmanagedAsyncMethod 인터페이스
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: 0b8adba9dbffbdc47bb526cef9aad3ffa4b48065
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129221"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="8bb27-102">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bb27-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="8bb27-103">이 인터페이스는 [ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)에 대 한 읽기 보수입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb27-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bb27-104">구문</span><span class="sxs-lookup"><span data-stu-id="8bb27-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="8bb27-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8bb27-105">Methods</span></span>  
 <span data-ttu-id="8bb27-106">이 인터페이스에는 다음과 같은 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb27-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="8bb27-107">메서드</span><span class="sxs-lookup"><span data-stu-id="8bb27-107">Method</span></span>|<span data-ttu-id="8bb27-108">설명</span><span class="sxs-lookup"><span data-stu-id="8bb27-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8bb27-109">GetAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="8bb27-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="8bb27-110">[DefineAsyncStepInfo 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8bb27-110">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="8bb27-111">GetAsyncStepInfoCount 메서드</span><span class="sxs-lookup"><span data-stu-id="8bb27-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="8bb27-112">[DefineAsyncStepInfo 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8bb27-112">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="8bb27-113">GetCatchHandlerILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="8bb27-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="8bb27-114">정의 [Ecatchhandleriloffset 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8bb27-114">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="8bb27-115">GetKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="8bb27-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="8bb27-116">[DefineKickoffMethod 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8bb27-116">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="8bb27-117">HasCatchHandlerILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="8bb27-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="8bb27-118">정의 [Ecatchhandleriloffset 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8bb27-118">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="8bb27-119">IsAsyncMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="8bb27-119">IsAsyncMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="8bb27-120">메서드에 비동기 정보가 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb27-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="8bb27-121">이 메서드가 `FALSE` 반환 하는 경우이 인터페이스의 다른 메서드를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb27-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="8bb27-122">이 경우 모두 `E_UNEXPECTED` 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bb27-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8bb27-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bb27-123">Requirements</span></span>  
 <span data-ttu-id="8bb27-124">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="8bb27-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bb27-125">참조</span><span class="sxs-lookup"><span data-stu-id="8bb27-125">See also</span></span>

- [<span data-ttu-id="8bb27-126">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bb27-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

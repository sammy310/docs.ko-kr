---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 메서드
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d000e61736f3250c677014cce50a2b7dcdecf1b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491689"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="65a78-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="65a78-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="65a78-103">비동기 메서드를 래핑하는 컴파일러에서 생성 된 catch 처리기에 대 한 오프셋 IL을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65a78-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="65a78-104">생성 된 catch의 IL 오프셋 사용자 코드 메서드에서 발생할 수 있습니다 하는 경우에 사용자 코드가 아닌 것 처럼 catch를 처리 하도록 디버거에 의해 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65a78-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="65a78-105">특히 대 한 응답으로 사용 되는 **CatchHandlerFound** 예외 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="65a78-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65a78-106">구문</span><span class="sxs-lookup"><span data-stu-id="65a78-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65a78-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="65a78-107">Parameters</span></span>  
  
|<span data-ttu-id="65a78-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="65a78-108">Parameter</span></span>|<span data-ttu-id="65a78-109">설명</span><span class="sxs-lookup"><span data-stu-id="65a78-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="65a78-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="65a78-110">Return Value</span></span>  
 <span data-ttu-id="65a78-111">`HRESULT`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="65a78-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65a78-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="65a78-112">Requirements</span></span>  
 <span data-ttu-id="65a78-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="65a78-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65a78-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="65a78-114">See also</span></span>
- [<span data-ttu-id="65a78-115">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65a78-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)

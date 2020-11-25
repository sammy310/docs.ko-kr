---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 메서드
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
ms.openlocfilehash: a37d319a39b959700944f9e111d2945e286c99ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707141"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="791ff-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="791ff-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>

<span data-ttu-id="791ff-103">비동기 메서드를 래핑하는 컴파일러 생성 catch 처리기에 대 한 IL 오프셋을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="791ff-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="791ff-104">생성 된 catch의 IL 오프셋은 디버거에서 사용자 코드 메서드에서 발생할 수 있는 경우에도 사용자가 작성 하지 않은 코드 였던 것 처럼 catch를 처리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="791ff-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="791ff-105">특히 **CatchHandlerFound** exception 이벤트에 대 한 응답에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="791ff-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="791ff-106">구문</span><span class="sxs-lookup"><span data-stu-id="791ff-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="791ff-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="791ff-107">Parameters</span></span>  
  
|<span data-ttu-id="791ff-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="791ff-108">Parameter</span></span>|<span data-ttu-id="791ff-109">설명</span><span class="sxs-lookup"><span data-stu-id="791ff-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="791ff-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="791ff-110">Return Value</span></span>  

 <span data-ttu-id="791ff-111">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="791ff-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="791ff-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="791ff-112">Requirements</span></span>  

 <span data-ttu-id="791ff-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="791ff-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="791ff-114">참조</span><span class="sxs-lookup"><span data-stu-id="791ff-114">See also</span></span>

- [<span data-ttu-id="791ff-115">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="791ff-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)

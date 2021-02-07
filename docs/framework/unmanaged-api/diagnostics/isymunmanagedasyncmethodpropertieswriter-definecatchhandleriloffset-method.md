---
description: ISymUnmanagedAsyncMethodPropertiesWriter::D efineCatchHandlerILOffset 메서드에 대해 자세히 알아보세요.
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 메서드
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
ms.openlocfilehash: fcb2c6efa7ea83252a46a9b08cdfa7b2c14f09d1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737794"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="d4c1b-103">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="d4c1b-103">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>

<span data-ttu-id="d4c1b-104">비동기 메서드를 래핑하는 컴파일러 생성 catch 처리기에 대 한 IL 오프셋을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4c1b-104">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="d4c1b-105">생성 된 catch의 IL 오프셋은 디버거에서 사용자 코드 메서드에서 발생할 수 있는 경우에도 사용자가 작성 하지 않은 코드 였던 것 처럼 catch를 처리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4c1b-105">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="d4c1b-106">특히 **CatchHandlerFound** exception 이벤트에 대 한 응답에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4c1b-106">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4c1b-107">구문</span><span class="sxs-lookup"><span data-stu-id="d4c1b-107">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4c1b-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d4c1b-108">Parameters</span></span>  
  
|<span data-ttu-id="d4c1b-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d4c1b-109">Parameter</span></span>|<span data-ttu-id="d4c1b-110">설명</span><span class="sxs-lookup"><span data-stu-id="d4c1b-110">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="d4c1b-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="d4c1b-111">Return Value</span></span>  

 <span data-ttu-id="d4c1b-112">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d4c1b-112">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4c1b-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d4c1b-113">Requirements</span></span>  

 <span data-ttu-id="d4c1b-114">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="d4c1b-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4c1b-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4c1b-115">See also</span></span>

- [<span data-ttu-id="d4c1b-116">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d4c1b-116">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)

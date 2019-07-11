---
title: ISymUnmanagedMethod::GetOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetOffset
helpviewer_keywords:
- GetOffset method, ISymUnmanagedMethod interface [.NET Framework debugging]
- ISymUnmanagedMethod::GetOffset method [.NET Framework debugging]
ms.assetid: 8bf3cb62-89bf-4159-ad53-de606aba89e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 62fa0969044504905d5c835f74873dc6f46cafa8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769432"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="aa1be-102">ISymUnmanagedMethod::GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="aa1be-102">ISymUnmanagedMethod::GetOffset Method</span></span>
<span data-ttu-id="aa1be-103">문서 내의 지정된 된 위치에 해당 하는이 메서드 내에서 오프셋을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa1be-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa1be-104">구문</span><span class="sxs-lookup"><span data-stu-id="aa1be-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa1be-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aa1be-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="aa1be-106">[in] 오프셋이 요청 된 문서에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aa1be-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="aa1be-107">[in] 오프셋이 요청 된 문서 줄.</span><span class="sxs-lookup"><span data-stu-id="aa1be-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="aa1be-108">[in] 오프셋이 요청 된 문서 열입니다.</span><span class="sxs-lookup"><span data-stu-id="aa1be-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="aa1be-109">[out] 에 대 한 포인터를 `ULONG32` 오프셋을 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="aa1be-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa1be-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="aa1be-110">Return Value</span></span>  
 <span data-ttu-id="aa1be-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="aa1be-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa1be-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa1be-112">Requirements</span></span>  
 <span data-ttu-id="aa1be-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="aa1be-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa1be-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="aa1be-114">See also</span></span>

- [<span data-ttu-id="aa1be-115">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa1be-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

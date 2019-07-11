---
title: ISymUnmanagedReader::GetMethodFromDocumentPosition 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a1935b831902e975616557f512789c339baf49c5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776982"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="17310-102">ISymUnmanagedReader::GetMethodFromDocumentPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="17310-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>
<span data-ttu-id="17310-103">문서에서 지정된 된 위치에 중단점을 포함 하는 메서드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="17310-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17310-104">구문</span><span class="sxs-lookup"><span data-stu-id="17310-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17310-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="17310-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="17310-106">[in] 지정 된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="17310-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="17310-107">[in] 지정 된 문서 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="17310-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="17310-108">[in] 지정 된 문서 열입니다.</span><span class="sxs-lookup"><span data-stu-id="17310-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="17310-109">[out] 주소에 대 한 포인터를 [ISymUnmanagedMethod 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) 중단점을 포함 하는 메서드를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="17310-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17310-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="17310-110">Return Value</span></span>  
 <span data-ttu-id="17310-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="17310-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17310-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="17310-112">Requirements</span></span>  
 <span data-ttu-id="17310-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="17310-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17310-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="17310-114">See also</span></span>

- [<span data-ttu-id="17310-115">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="17310-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

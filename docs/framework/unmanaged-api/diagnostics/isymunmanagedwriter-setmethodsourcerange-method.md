---
title: ISymUnmanagedWriter::SetMethodSourceRange 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetMethodSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 46072718a7dafc0a00294757d5ccce6242a11e23
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468366"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="69ba6-102">ISymUnmanagedWriter::SetMethodSourceRange 메서드</span><span class="sxs-lookup"><span data-stu-id="69ba6-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>
<span data-ttu-id="69ba6-103">True 이면 시작 및 끝 소스 파일 내의 메서드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69ba6-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="69ba6-104">이 메서드를 사용 하 여 메서드 내에 있는 시퀀스 위치의 독립적으로 메서드의 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="69ba6-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69ba6-105">구문</span><span class="sxs-lookup"><span data-stu-id="69ba6-105">Syntax</span></span>  
  
```  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69ba6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="69ba6-106">Parameters</span></span>  
 `startDoc`  
 <span data-ttu-id="69ba6-107">[in] 시작 위치를 포함 하는 문서에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="69ba6-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="69ba6-108">[in] 시작 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="69ba6-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="69ba6-109">[in] 시작 열입니다.</span><span class="sxs-lookup"><span data-stu-id="69ba6-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="69ba6-110">[in] 끝 위치를 포함 하는 문서에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="69ba6-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="69ba6-111">[in] 끝 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="69ba6-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="69ba6-112">[in] 끝 열 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="69ba6-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69ba6-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="69ba6-113">Return Value</span></span>  
 <span data-ttu-id="69ba6-114">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="69ba6-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69ba6-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69ba6-115">Requirements</span></span>  
 <span data-ttu-id="69ba6-116">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="69ba6-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69ba6-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="69ba6-117">See also</span></span>
- [<span data-ttu-id="69ba6-118">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69ba6-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

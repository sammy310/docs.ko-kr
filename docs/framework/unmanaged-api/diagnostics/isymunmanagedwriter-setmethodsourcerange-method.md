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
ms.openlocfilehash: 85e65f6a3ec13c2acc31b8f87dbe4b4476ffc2a5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427872"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="60212-102">ISymUnmanagedWriter::SetMethodSourceRange 메서드</span><span class="sxs-lookup"><span data-stu-id="60212-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>
<span data-ttu-id="60212-103">True 이면 시작 및 끝 소스 파일 내의 메서드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="60212-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="60212-104">이 메서드를 사용 하 여 메서드 내에 있는 시퀀스 위치와 독립적으로 메서드 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="60212-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60212-105">구문</span><span class="sxs-lookup"><span data-stu-id="60212-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60212-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="60212-106">Parameters</span></span>  
 `startDoc`  
 <span data-ttu-id="60212-107">진행 시작 위치를 포함 하는 문서에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="60212-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="60212-108">진행 시작 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="60212-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="60212-109">진행 시작 열입니다.</span><span class="sxs-lookup"><span data-stu-id="60212-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="60212-110">진행 끝 위치를 포함 하는 문서에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="60212-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="60212-111">진행 끝 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="60212-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="60212-112">진행 끝 열 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="60212-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60212-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="60212-113">Return Value</span></span>  
 <span data-ttu-id="60212-114">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="60212-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60212-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="60212-115">Requirements</span></span>  
 <span data-ttu-id="60212-116">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="60212-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60212-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60212-117">See also</span></span>

- [<span data-ttu-id="60212-118">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60212-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

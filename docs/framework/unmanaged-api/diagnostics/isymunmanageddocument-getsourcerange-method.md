---
title: ISymUnmanagedDocument::GetSourceRange 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 981048c10be27900f011afeab55d1c5eb523f734
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776674"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a><span data-ttu-id="a25f0-102">ISymUnmanagedDocument::GetSourceRange 메서드</span><span class="sxs-lookup"><span data-stu-id="a25f0-102">ISymUnmanagedDocument::GetSourceRange Method</span></span>
<span data-ttu-id="a25f0-103">지정 된 버퍼에 지정된 된 포함된 된 소스 범위를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a25f0-103">Returns the specified range of the embedded source into the given buffer.</span></span> <span data-ttu-id="a25f0-104">버퍼는 소스를 포함할 수 있는 크기 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25f0-104">The buffer must be large enough to hold the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a25f0-105">구문</span><span class="sxs-lookup"><span data-stu-id="a25f0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a25f0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a25f0-106">Parameters</span></span>  
 `startLine`  
 <span data-ttu-id="a25f0-107">[in] 현재 문서의 시작 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="a25f0-107">[in] The starting line in the current document.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="a25f0-108">[in] 현재 문서의 시작 열입니다.</span><span class="sxs-lookup"><span data-stu-id="a25f0-108">[in] The starting column in the current document.</span></span>  
  
 `endLine`  
 <span data-ttu-id="a25f0-109">[in] 현재 문서의 마지막 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="a25f0-109">[in] The final line in the current document.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="a25f0-110">[in] 현재 문서의 마지막 열입니다.</span><span class="sxs-lookup"><span data-stu-id="a25f0-110">[in] The final column in the current document.</span></span>  
  
 `cSourceBytes`  
 <span data-ttu-id="a25f0-111">[in] 크기 (바이트)에서 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="a25f0-111">[in] The size of the source, in bytes.</span></span>  
  
 `pcSourceBytes`  
 <span data-ttu-id="a25f0-112">[out] 원본 크기를 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a25f0-112">[out] A pointer to a variable that receives the source size.</span></span>  
  
 `source`  
 <span data-ttu-id="a25f0-113">[out] 크기 및 소스 문서의 바이트 단위로 지정 된 범위의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="a25f0-113">[out] The size and length of the specified range of the source document, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a25f0-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="a25f0-114">Return Value</span></span>  
 <span data-ttu-id="a25f0-115">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="a25f0-115">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a25f0-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="a25f0-116">See also</span></span>

- [<span data-ttu-id="a25f0-117">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a25f0-117">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

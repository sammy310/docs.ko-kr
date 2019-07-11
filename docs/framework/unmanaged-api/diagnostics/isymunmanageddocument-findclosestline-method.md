---
title: ISymUnmanagedDocument::FindClosestLine 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8d6be64137b59c84dfadbd7f0e4895eac2fb27e4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776789"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="7e4b4-102">ISymUnmanagedDocument::FindClosestLine 메서드</span><span class="sxs-lookup"><span data-stu-id="7e4b4-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="7e4b4-103">줄 시퀀스 위치가 될 수 있고이 문서에 지정 된 시퀀스 위치가 되는 가장 가까운 줄을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e4b4-104">구문</span><span class="sxs-lookup"><span data-stu-id="7e4b4-104">Syntax</span></span>  
  
```cpp  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e4b4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7e4b4-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="7e4b4-106">[in] 이 문서의 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="7e4b4-107">[out] 줄을 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e4b4-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="7e4b4-108">Return Value</span></span>  
 <span data-ttu-id="7e4b4-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e4b4-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="7e4b4-110">See also</span></span>

- [<span data-ttu-id="7e4b4-111">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e4b4-111">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

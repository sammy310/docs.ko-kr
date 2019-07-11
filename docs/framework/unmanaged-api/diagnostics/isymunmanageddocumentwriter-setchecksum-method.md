---
title: ISymUnmanagedDocumentWriter::SetCheckSum 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum method [.NET Framework debugging]
- SetCheckSum method [.NET Framework debugging]
ms.assetid: c7e99879-421f-43ce-b193-34733cf30085
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3343710fbe4f1aba8c38e46a0a720f78944a1c10
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776931"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="9faa4-102">ISymUnmanagedDocumentWriter::SetCheckSum 메서드</span><span class="sxs-lookup"><span data-stu-id="9faa4-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="9faa4-103">체크섬 정보를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9faa4-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9faa4-104">구문</span><span class="sxs-lookup"><span data-stu-id="9faa4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9faa4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9faa4-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="9faa4-106">[in] 알고리즘 식별자를 나타내는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="9faa4-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="9faa4-107">[in] A `ULONG32` 의 크기 (바이트) 나타내는 `checkSum` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="9faa4-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="9faa4-108">[in] 체크섬 정보를 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="9faa4-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9faa4-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="9faa4-109">Return Value</span></span>  
 <span data-ttu-id="9faa4-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="9faa4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9faa4-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9faa4-111">Requirements</span></span>  
 <span data-ttu-id="9faa4-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9faa4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9faa4-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="9faa4-113">See also</span></span>

- [<span data-ttu-id="9faa4-114">ISymUnmanagedDocumentWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9faa4-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)

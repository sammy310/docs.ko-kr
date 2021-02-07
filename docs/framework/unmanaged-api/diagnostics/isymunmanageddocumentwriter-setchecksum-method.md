---
description: '자세히 알아보기: ISymUnmanagedDocumentWriter:: SetCheckSum 메서드'
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
ms.openlocfilehash: ac2ba9654f3610dca333cf0e06c20696cf31bd1f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710090"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="09774-103">ISymUnmanagedDocumentWriter::SetCheckSum 메서드</span><span class="sxs-lookup"><span data-stu-id="09774-103">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>

<span data-ttu-id="09774-104">체크섬 정보를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="09774-104">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09774-105">구문</span><span class="sxs-lookup"><span data-stu-id="09774-105">Syntax</span></span>  
  
```cpp  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09774-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="09774-106">Parameters</span></span>  

 `algorithmId`  
 <span data-ttu-id="09774-107">진행 알고리즘 식별자를 나타내는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="09774-107">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="09774-108">진행 `ULONG32` 버퍼의 크기 (바이트)를 나타내는입니다 `checkSum` .</span><span class="sxs-lookup"><span data-stu-id="09774-108">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="09774-109">진행 체크섬 정보를 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="09774-109">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09774-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="09774-110">Return Value</span></span>  

 <span data-ttu-id="09774-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="09774-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09774-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09774-112">Requirements</span></span>  

 <span data-ttu-id="09774-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="09774-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09774-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09774-114">See also</span></span>

- [<span data-ttu-id="09774-115">ISymUnmanagedDocumentWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09774-115">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)

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
ms.openlocfilehash: 58055d9ea56d7928729d289198965752985d8e0c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688902"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="c8dc9-102">ISymUnmanagedDocumentWriter::SetCheckSum 메서드</span><span class="sxs-lookup"><span data-stu-id="c8dc9-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>

<span data-ttu-id="c8dc9-103">체크섬 정보를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8dc9-104">구문</span><span class="sxs-lookup"><span data-stu-id="c8dc9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8dc9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8dc9-105">Parameters</span></span>  

 `algorithmId`  
 <span data-ttu-id="c8dc9-106">진행 알고리즘 식별자를 나타내는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="c8dc9-107">진행 `ULONG32` 버퍼의 크기 (바이트)를 나타내는입니다 `checkSum` .</span><span class="sxs-lookup"><span data-stu-id="c8dc9-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="c8dc9-108">진행 체크섬 정보를 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8dc9-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="c8dc9-109">Return Value</span></span>  

 <span data-ttu-id="c8dc9-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8dc9-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8dc9-111">Requirements</span></span>  

 <span data-ttu-id="c8dc9-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="c8dc9-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8dc9-113">참조</span><span class="sxs-lookup"><span data-stu-id="c8dc9-113">See also</span></span>

- [<span data-ttu-id="c8dc9-114">ISymUnmanagedDocumentWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8dc9-114">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)

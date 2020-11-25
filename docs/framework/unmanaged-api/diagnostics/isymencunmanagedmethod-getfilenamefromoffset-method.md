---
title: ISymENCUnmanagedMethod::GetFileNameFromOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetFileNameFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetFileNameFromOffset
helpviewer_keywords:
- GetFileNameFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetFileNameFromOffset method [.NET Framework debugging]
ms.assetid: 00e2e194-12f5-436e-a997-2b9d3e844d4f
topic_type:
- apiref
ms.openlocfilehash: ad9631039c8d032e7ffdba1e6098b66398f82277
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707388"
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a><span data-ttu-id="4c196-102">ISymENCUnmanagedMethod::GetFileNameFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="4c196-102">ISymENCUnmanagedMethod::GetFileNameFromOffset Method</span></span>

<span data-ttu-id="4c196-103">오프셋과 연결 된 줄의 파일 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4c196-103">Gets the file name for the line associated with an offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c196-104">구문</span><span class="sxs-lookup"><span data-stu-id="4c196-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c196-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4c196-105">Parameters</span></span>  

 `dwOffset`  
 <span data-ttu-id="4c196-106">진행 `ULONG32` 오프셋을 포함 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="4c196-106">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `cchName`  
 <span data-ttu-id="4c196-107">진행 `ULONG32` 버퍼의 크기를 나타내는입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="4c196-107">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="4c196-108">제한이 `ULONG32` 파일 이름을 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4c196-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the file names.</span></span>  
  
 `szName`  
 <span data-ttu-id="4c196-109">제한이 파일 이름을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="4c196-109">[out] The buffer that contains the file names.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c196-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="4c196-110">Return Value</span></span>  

 <span data-ttu-id="4c196-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4c196-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c196-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4c196-112">Requirements</span></span>  

 <span data-ttu-id="4c196-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="4c196-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c196-114">참조</span><span class="sxs-lookup"><span data-stu-id="4c196-114">See also</span></span>

- [<span data-ttu-id="4c196-115">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4c196-115">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)

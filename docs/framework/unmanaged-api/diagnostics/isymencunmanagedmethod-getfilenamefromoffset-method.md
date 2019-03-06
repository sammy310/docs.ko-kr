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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: df1e9d317294127a931bebf100295290a0dd6b23
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471838"
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a><span data-ttu-id="2dcd8-102">ISymENCUnmanagedMethod::GetFileNameFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="2dcd8-102">ISymENCUnmanagedMethod::GetFileNameFromOffset Method</span></span>
<span data-ttu-id="2dcd8-103">줄 오프셋을 사용 하 여 연결에 대 한 파일 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2dcd8-103">Gets the file name for the line associated with an offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dcd8-104">구문</span><span class="sxs-lookup"><span data-stu-id="2dcd8-104">Syntax</span></span>  
  
```  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2dcd8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2dcd8-105">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="2dcd8-106">[in] `ULONG32` 오프셋을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcd8-106">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `cchName`  
 <span data-ttu-id="2dcd8-107">[in] A `ULONG32` 의 크기를 나타내는 `szName` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="2dcd8-107">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="2dcd8-108">[out] 에 대 한 포인터를 `ULONG32` 문자의 파일 이름을 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcd8-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the file names.</span></span>  
  
 `szName`  
 <span data-ttu-id="2dcd8-109">[out] 파일 이름을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="2dcd8-109">[out] The buffer that contains the file names.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2dcd8-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="2dcd8-110">Return Value</span></span>  
 <span data-ttu-id="2dcd8-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2dcd8-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dcd8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2dcd8-112">Requirements</span></span>  
 <span data-ttu-id="2dcd8-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2dcd8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dcd8-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="2dcd8-114">See also</span></span>
- [<span data-ttu-id="2dcd8-115">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dcd8-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)

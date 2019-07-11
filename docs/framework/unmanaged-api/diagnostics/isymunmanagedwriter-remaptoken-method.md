---
title: ISymUnmanagedWriter::RemapToken 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c04ca1d56f3e93c77f335218bb534f890e9053d2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776616"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="fd553-102">ISymUnmanagedWriter::RemapToken 메서드</span><span class="sxs-lookup"><span data-stu-id="fd553-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="fd553-103">메타 데이터를 내보낼 때 메타 데이터 토큰을 다시 매핑할 된 기호 작성기를에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fd553-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="fd553-104">기호 작성기가 이전 토큰 기호 저장소에 저장 하는 경우에 업데이트를 하거나 새 값 또는를 사용 하 여 저장된 된 토큰이 읽기 단계를 다시 매핑할 해당 기호 판독기에 대 한 맵을 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd553-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd553-105">구문</span><span class="sxs-lookup"><span data-stu-id="fd553-105">Syntax</span></span>  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd553-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fd553-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="fd553-107">[in] 메타 데이터 토큰 다시 매핑된입니다.</span><span class="sxs-lookup"><span data-stu-id="fd553-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="fd553-108">[in] 새 메타 데이터 토큰 `oldToken` 다시 매핑된 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd553-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd553-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="fd553-109">Return Value</span></span>  
 <span data-ttu-id="fd553-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="fd553-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd553-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd553-111">Requirements</span></span>  
 <span data-ttu-id="fd553-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fd553-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd553-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="fd553-113">See also</span></span>

- [<span data-ttu-id="fd553-114">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fd553-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

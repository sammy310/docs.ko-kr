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
ms.openlocfilehash: 9e441d4ff39632d9381e445ee99249d04539ad87
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427878"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="af85a-102">ISymUnmanagedWriter::RemapToken 메서드</span><span class="sxs-lookup"><span data-stu-id="af85a-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="af85a-103">메타 데이터를 내보낼 때 메타 데이터 토큰이 다시 매핑되고 있음을 기호 작성기에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="af85a-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="af85a-104">기호 작성기가 기호 저장소 내에 이전 토큰을 저장 한 경우 저장 된 토큰을 새 값으로 업데이트 해야 합니다. 그렇지 않으면 읽기 단계에서 다시 매핑할 해당 기호 판독기에 대 한 맵을 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af85a-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af85a-105">구문</span><span class="sxs-lookup"><span data-stu-id="af85a-105">Syntax</span></span>  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af85a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="af85a-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="af85a-107">진행 다시 매핑된 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="af85a-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="af85a-108">진행 `oldToken` 다시 매핑되는 새 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="af85a-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af85a-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="af85a-109">Return Value</span></span>  
 <span data-ttu-id="af85a-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="af85a-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af85a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af85a-111">Requirements</span></span>  
 <span data-ttu-id="af85a-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="af85a-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af85a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af85a-113">See also</span></span>

- [<span data-ttu-id="af85a-114">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af85a-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

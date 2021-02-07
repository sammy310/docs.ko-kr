---
description: '자세히 알아보기: ISymUnmanagedWriter:: RemapToken 메서드'
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
ms.openlocfilehash: c065d42c3d2749f0262fdd81a74de918274ba67d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762086"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="fefbe-103">ISymUnmanagedWriter::RemapToken 메서드</span><span class="sxs-lookup"><span data-stu-id="fefbe-103">ISymUnmanagedWriter::RemapToken Method</span></span>

<span data-ttu-id="fefbe-104">메타 데이터를 내보낼 때 메타 데이터 토큰이 다시 매핑되고 있음을 기호 작성기에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fefbe-104">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="fefbe-105">기호 작성기가 기호 저장소 내에 이전 토큰을 저장 한 경우 저장 된 토큰을 새 값으로 업데이트 해야 합니다. 그렇지 않으면 읽기 단계에서 다시 매핑할 해당 기호 판독기에 대 한 맵을 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefbe-105">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fefbe-106">구문</span><span class="sxs-lookup"><span data-stu-id="fefbe-106">Syntax</span></span>  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fefbe-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fefbe-107">Parameters</span></span>  

 `oldToken`  
 <span data-ttu-id="fefbe-108">진행 다시 매핑된 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="fefbe-108">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="fefbe-109">진행 가 다시 매핑되는 새 메타 데이터 토큰입니다 `oldToken` .</span><span class="sxs-lookup"><span data-stu-id="fefbe-109">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fefbe-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="fefbe-110">Return Value</span></span>  

 <span data-ttu-id="fefbe-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="fefbe-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fefbe-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fefbe-112">Requirements</span></span>  

 <span data-ttu-id="fefbe-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="fefbe-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fefbe-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fefbe-114">See also</span></span>

- [<span data-ttu-id="fefbe-115">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fefbe-115">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)

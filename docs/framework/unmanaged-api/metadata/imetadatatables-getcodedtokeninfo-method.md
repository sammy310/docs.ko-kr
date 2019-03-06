---
title: IMetaDataTables::GetCodedTokenInfo 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetCodedTokenInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetCodedTokenInfo
helpviewer_keywords:
- GetCodedTokenInfo method [.NET Framework metadata]
- IMetaDataTables::GetCodedTokenInfo method [.NET Framework metadata]
ms.assetid: 31214d3a-715e-49af-92b3-0fd11e4f218a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1a9eb51643271fd27a6d4795fc1729766b44b239
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468795"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="b062d-102">IMetaDataTables::GetCodedTokenInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="b062d-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="b062d-103">지정된 된 행 인덱스와 연결 된 토큰의 배열에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b062d-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b062d-104">구문</span><span class="sxs-lookup"><span data-stu-id="b062d-104">Syntax</span></span>  
  
```  
HRESULT GetCodedTokenInfo (   
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b062d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b062d-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="b062d-106">[in] 반환할 코딩 된 토큰의 종류입니다.</span><span class="sxs-lookup"><span data-stu-id="b062d-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b062d-107">[out] 길이에 대 한 포인터 `ppTokens`합니다.</span><span class="sxs-lookup"><span data-stu-id="b062d-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="b062d-108">[out] 반환 된 토큰의 목록을 포함 하는 배열에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b062d-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="b062d-109">[out] 토큰의 이름에 대 한 포인터에 대 한 포인터 `ixCdTkn`합니다.</span><span class="sxs-lookup"><span data-stu-id="b062d-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b062d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b062d-110">Requirements</span></span>  
 <span data-ttu-id="b062d-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b062d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b062d-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b062d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b062d-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="b062d-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b062d-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b062d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b062d-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="b062d-115">See also</span></span>
- [<span data-ttu-id="b062d-116">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b062d-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="b062d-117">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b062d-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)

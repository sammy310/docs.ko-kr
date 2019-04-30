---
title: IMetaDataTables::GetBlob 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: babe098b16729cfcd41b48075a49b9ae9be7dfdc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049806"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="0de95-102">IMetaDataTables::GetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="0de95-102">IMetaDataTables::GetBlob Method</span></span>
<span data-ttu-id="0de95-103">Binary large object (BLOB)를 지정 된 열 인덱스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0de95-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0de95-104">구문</span><span class="sxs-lookup"><span data-stu-id="0de95-104">Syntax</span></span>  
  
```  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0de95-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0de95-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="0de95-106">[in] 메모리 주소를 가져올 `ppData`합니다.</span><span class="sxs-lookup"><span data-stu-id="0de95-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="0de95-107">[out] 크기 (바이트)에 대 한 포인터의 `ppData`합니다.</span><span class="sxs-lookup"><span data-stu-id="0de95-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="0de95-108">[out] 이진 데이터에 대 한 포인터에 대 한 포인터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="0de95-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0de95-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0de95-109">Requirements</span></span>  
 <span data-ttu-id="0de95-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0de95-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0de95-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0de95-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0de95-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="0de95-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0de95-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0de95-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0de95-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="0de95-114">See also</span></span>

- [<span data-ttu-id="0de95-115">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0de95-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="0de95-116">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0de95-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)

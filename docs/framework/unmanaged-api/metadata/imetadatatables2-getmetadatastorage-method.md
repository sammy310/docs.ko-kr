---
title: IMetaDataTables2::GetMetaDataStorage 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStorage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStorage
helpviewer_keywords:
- GetMetaDataStorage method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStorage method [.NET Framework metadata]
ms.assetid: 667a6d1e-753d-4ea2-8fd8-a8337d1bb9cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1c177a315a76009b7ac82055cba2d0b23821333b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494884"
---
# <a name="imetadatatables2getmetadatastorage-method"></a><span data-ttu-id="6c7f7-102">IMetaDataTables2::GetMetaDataStorage 메서드</span><span class="sxs-lookup"><span data-stu-id="6c7f7-102">IMetaDataTables2::GetMetaDataStorage Method</span></span>
<span data-ttu-id="6c7f7-103">지정된 된 섹션에 저장 된 메타 데이터의 내용을 확인 하 고 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6c7f7-103">Gets the size and contents of the metadata stored in the specified section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c7f7-104">구문</span><span class="sxs-lookup"><span data-stu-id="6c7f7-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c7f7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6c7f7-105">Parameters</span></span>  
 `ppvMd`  
 <span data-ttu-id="6c7f7-106">[out에서] 메타 데이터 섹션에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7f7-106">[in, out] A pointer to a metadata section.</span></span>  
  
 `pcbMd`  
 <span data-ttu-id="6c7f7-107">[out] 메타 데이터 스트림 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7f7-107">[out] The size of the metadata stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c7f7-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c7f7-108">Requirements</span></span>  
 <span data-ttu-id="6c7f7-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6c7f7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c7f7-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6c7f7-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6c7f7-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="6c7f7-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6c7f7-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c7f7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c7f7-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="6c7f7-113">See also</span></span>
- [<span data-ttu-id="6c7f7-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c7f7-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [<span data-ttu-id="6c7f7-115">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c7f7-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)

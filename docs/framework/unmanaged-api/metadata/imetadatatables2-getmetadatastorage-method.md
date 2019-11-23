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
ms.openlocfilehash: 302e9db3bc683eaa2b65e0b0479de721e07d56db
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442648"
---
# <a name="imetadatatables2getmetadatastorage-method"></a><span data-ttu-id="75016-102">IMetaDataTables2::GetMetaDataStorage 메서드</span><span class="sxs-lookup"><span data-stu-id="75016-102">IMetaDataTables2::GetMetaDataStorage Method</span></span>
<span data-ttu-id="75016-103">Gets the size and contents of the metadata stored in the specified section.</span><span class="sxs-lookup"><span data-stu-id="75016-103">Gets the size and contents of the metadata stored in the specified section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75016-104">구문</span><span class="sxs-lookup"><span data-stu-id="75016-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75016-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="75016-105">Parameters</span></span>  
 `ppvMd`  
 <span data-ttu-id="75016-106">[in, out] A pointer to a metadata section.</span><span class="sxs-lookup"><span data-stu-id="75016-106">[in, out] A pointer to a metadata section.</span></span>  
  
 `pcbMd`  
 <span data-ttu-id="75016-107">[out] The size of the metadata stream.</span><span class="sxs-lookup"><span data-stu-id="75016-107">[out] The size of the metadata stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75016-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="75016-108">Requirements</span></span>  
 <span data-ttu-id="75016-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75016-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75016-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="75016-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="75016-111">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="75016-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="75016-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75016-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75016-113">참조</span><span class="sxs-lookup"><span data-stu-id="75016-113">See also</span></span>

- [<span data-ttu-id="75016-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75016-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [<span data-ttu-id="75016-115">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75016-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)

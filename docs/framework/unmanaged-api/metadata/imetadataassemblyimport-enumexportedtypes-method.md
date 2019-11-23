---
title: IMetaDataAssemblyImport::EnumExportedTypes 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
ms.openlocfilehash: 45e2348b4726447548544d975e60b93e464fb402
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450336"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="ac6dc-102">IMetaDataAssemblyImport::EnumExportedTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="ac6dc-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="ac6dc-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="ac6dc-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac6dc-104">구문</span><span class="sxs-lookup"><span data-stu-id="ac6dc-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac6dc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ac6dc-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ac6dc-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="ac6dc-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ac6dc-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span><span class="sxs-lookup"><span data-stu-id="ac6dc-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="ac6dc-108">[out] The enumeration of `mdExportedType` metadata tokens.</span><span class="sxs-lookup"><span data-stu-id="ac6dc-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ac6dc-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span><span class="sxs-lookup"><span data-stu-id="ac6dc-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="ac6dc-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span><span class="sxs-lookup"><span data-stu-id="ac6dc-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac6dc-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="ac6dc-111">Return Value</span></span>  
  
|<span data-ttu-id="ac6dc-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac6dc-112">HRESULT</span></span>|<span data-ttu-id="ac6dc-113">설명</span><span class="sxs-lookup"><span data-stu-id="ac6dc-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ac6dc-114">`EnumExportedTypes` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="ac6dc-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ac6dc-115">There are no tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="ac6dc-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="ac6dc-116">In this case, `pcTokens` is set to zero.</span><span class="sxs-lookup"><span data-stu-id="ac6dc-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ac6dc-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ac6dc-117">Requirements</span></span>  
 <span data-ttu-id="ac6dc-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac6dc-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac6dc-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ac6dc-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ac6dc-120">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac6dc-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ac6dc-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac6dc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac6dc-122">참조</span><span class="sxs-lookup"><span data-stu-id="ac6dc-122">See also</span></span>

- [<span data-ttu-id="ac6dc-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac6dc-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)

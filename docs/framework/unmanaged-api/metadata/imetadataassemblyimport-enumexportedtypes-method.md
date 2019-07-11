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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 62c44d0c3bd2e931b1708abb48bc9c854431419f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751142"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="b671c-102">IMetaDataAssemblyImport::EnumExportedTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="b671c-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="b671c-103">현재 메타 데이터 범위에서 어셈블리 매니페스트에서 참조 하는 내보낸된 형식을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b671c-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b671c-104">구문</span><span class="sxs-lookup"><span data-stu-id="b671c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b671c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b671c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b671c-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b671c-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b671c-107">Null 이어야 합니다 경우이 값은 `EnumExportedTypes` 처음으로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b671c-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="b671c-108">[out] 열거형 `mdExportedType` 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b671c-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b671c-109">[in] 최대 `mdExportedType` 에 배치할 수 있는 토큰을 `rExportedTypes` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b671c-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b671c-110">[out] 수가 `mdExportedType` 토큰에 실제로 배치 `rExportedTypes`합니다.</span><span class="sxs-lookup"><span data-stu-id="b671c-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b671c-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="b671c-111">Return Value</span></span>  
  
|<span data-ttu-id="b671c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b671c-112">HRESULT</span></span>|<span data-ttu-id="b671c-113">Description</span><span class="sxs-lookup"><span data-stu-id="b671c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b671c-114">`EnumExportedTypes` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b671c-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b671c-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b671c-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="b671c-116">이 경우 `pcTokens` 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b671c-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b671c-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b671c-117">Requirements</span></span>  
 <span data-ttu-id="b671c-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b671c-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b671c-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b671c-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b671c-120">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="b671c-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b671c-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b671c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b671c-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="b671c-122">See also</span></span>

- [<span data-ttu-id="b671c-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b671c-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)

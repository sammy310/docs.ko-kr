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
ms.openlocfilehash: f00fe5bce2f808265add228406dfaa2ccc267545
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176008"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="18a39-102">IMetaDataAssemblyImport::EnumExportedTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="18a39-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="18a39-103">어셈블리 매니페스트에서 참조되는 내보낸 형식을 현재 메타데이터 범위에서 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="18a39-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18a39-104">구문</span><span class="sxs-lookup"><span data-stu-id="18a39-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18a39-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18a39-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="18a39-106">【인, 아웃】 열거형에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="18a39-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="18a39-107">`EnumExportedTypes` 메서드를 처음 호출할 때 null 값이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18a39-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="18a39-108">【아웃】 메타데이터 토큰의 `mdExportedType` 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="18a39-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="18a39-109">【인】 배열에 배치할 수 있는 `mdExportedType` 최대 `rExportedTypes` 토큰 수입니다.</span><span class="sxs-lookup"><span data-stu-id="18a39-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="18a39-110">【아웃】 실제로 에 `mdExportedType` 배치된 토큰 `rExportedTypes`수입니다.</span><span class="sxs-lookup"><span data-stu-id="18a39-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18a39-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="18a39-111">Return Value</span></span>  
  
|<span data-ttu-id="18a39-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="18a39-112">HRESULT</span></span>|<span data-ttu-id="18a39-113">Description</span><span class="sxs-lookup"><span data-stu-id="18a39-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="18a39-114">`EnumExportedTypes`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="18a39-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="18a39-115">등록할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18a39-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="18a39-116">이 경우 `pcTokens` 0으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="18a39-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18a39-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18a39-117">Requirements</span></span>  
 <span data-ttu-id="18a39-118">**플랫폼:** [시스템 요구 사항을](../../../../docs/framework/get-started/system-requirements.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="18a39-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18a39-119">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="18a39-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="18a39-120">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="18a39-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="18a39-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18a39-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18a39-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18a39-122">See also</span></span>

- [<span data-ttu-id="18a39-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18a39-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)

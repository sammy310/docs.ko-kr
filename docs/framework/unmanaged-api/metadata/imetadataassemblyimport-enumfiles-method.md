---
title: IMetaDataAssemblyImport::EnumFiles 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumFiles
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type:
- apiref
ms.openlocfilehash: 70f76318f51047cb81262f744a6fbed5fe401692
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177810"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="86afe-102">IMetaDataAssemblyImport::EnumFiles 메서드</span><span class="sxs-lookup"><span data-stu-id="86afe-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="86afe-103">현재 어셈블리 매니페스트에서 참조하는 파일을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="86afe-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86afe-104">구문</span><span class="sxs-lookup"><span data-stu-id="86afe-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,
    [out] mdFile          rFiles[],
    [in]  ULONG           cMax,
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86afe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="86afe-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="86afe-106">【인, 아웃】 열거형에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="86afe-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="86afe-107">이 메서드의 첫 번째 호출에 대 한 null 값이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86afe-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="86afe-108">【아웃】 메타데이터 토큰을 `mdFile` 저장하는 데 사용되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="86afe-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="86afe-109">【인】 에 `rFiles`배치할 `mdFile` 수 있는 최대 토큰 수입니다.</span><span class="sxs-lookup"><span data-stu-id="86afe-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="86afe-110">【아웃】 실제로 에 `mdFile` 배치된 토큰 `rFiles`수입니다.</span><span class="sxs-lookup"><span data-stu-id="86afe-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86afe-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="86afe-111">Return Value</span></span>  
  
|<span data-ttu-id="86afe-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="86afe-112">HRESULT</span></span>|<span data-ttu-id="86afe-113">Description</span><span class="sxs-lookup"><span data-stu-id="86afe-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="86afe-114">`EnumFiles`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="86afe-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="86afe-115">등록할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86afe-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="86afe-116">이 경우 `pcTokens` 0으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="86afe-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="86afe-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="86afe-117">Requirements</span></span>  
 <span data-ttu-id="86afe-118">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="86afe-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86afe-119">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="86afe-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="86afe-120">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="86afe-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="86afe-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86afe-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86afe-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86afe-122">See also</span></span>

- [<span data-ttu-id="86afe-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86afe-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)

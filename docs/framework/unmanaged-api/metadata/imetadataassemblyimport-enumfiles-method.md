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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b2ab06419491093a2de41d2ef25d16c01c03ebaf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158849"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="92156-102">IMetaDataAssemblyImport::EnumFiles 메서드</span><span class="sxs-lookup"><span data-stu-id="92156-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="92156-103">현재 어셈블리 매니페스트에서 참조 하는 파일을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="92156-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92156-104">구문</span><span class="sxs-lookup"><span data-stu-id="92156-104">Syntax</span></span>  
  
```  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,   
    [out] mdFile          rFiles[],   
    [in]  ULONG           cMax,   
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92156-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="92156-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="92156-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="92156-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="92156-107">이 메서드의 첫 번째 호출에 대 한 null 값 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92156-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="92156-108">[out] 배열을 저장 하는 데는 `mdFile` 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="92156-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="92156-109">[in] 최대 `mdFile` 에 배치할 수 있는 토큰 `rFiles`합니다.</span><span class="sxs-lookup"><span data-stu-id="92156-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="92156-110">[out] 수가 `mdFile` 토큰에 실제로 배치 `rFiles`합니다.</span><span class="sxs-lookup"><span data-stu-id="92156-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92156-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="92156-111">Return Value</span></span>  
  
|<span data-ttu-id="92156-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="92156-112">HRESULT</span></span>|<span data-ttu-id="92156-113">설명</span><span class="sxs-lookup"><span data-stu-id="92156-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumFiles` <span data-ttu-id="92156-114">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="92156-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="92156-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92156-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="92156-116">이 경우 `pcTokens` 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92156-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="92156-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="92156-117">Requirements</span></span>  
 <span data-ttu-id="92156-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="92156-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92156-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="92156-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92156-120">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="92156-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="92156-121">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="92156-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="92156-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="92156-122">See also</span></span>

- [<span data-ttu-id="92156-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="92156-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)

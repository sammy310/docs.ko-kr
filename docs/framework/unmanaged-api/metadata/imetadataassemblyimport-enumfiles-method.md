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
ms.openlocfilehash: e4549789ea1af584c0850a535d9f6bb54f844ce0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443549"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="b611c-102">IMetaDataAssemblyImport::EnumFiles 메서드</span><span class="sxs-lookup"><span data-stu-id="b611c-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="b611c-103">현재 어셈블리 매니페스트에서 참조 하는 파일을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b611c-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b611c-104">구문</span><span class="sxs-lookup"><span data-stu-id="b611c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,   
    [out] mdFile          rFiles[],   
    [in]  ULONG           cMax,   
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b611c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b611c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b611c-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b611c-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b611c-107">이 메서드의 첫 번째 호출에는 null 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b611c-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="b611c-108">제한이 `mdFile` 메타 데이터 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b611c-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b611c-109">진행 `rFiles`에 배치할 수 있는 `mdFile` 토큰의 최대 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b611c-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b611c-110">제한이 `rFiles`에 실제로 배치 된 `mdFile` 토큰 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b611c-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b611c-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="b611c-111">Return Value</span></span>  
  
|<span data-ttu-id="b611c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b611c-112">HRESULT</span></span>|<span data-ttu-id="b611c-113">설명</span><span class="sxs-lookup"><span data-stu-id="b611c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b611c-114">`EnumFiles` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b611c-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b611c-115">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b611c-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="b611c-116">이 경우 `pcTokens`은 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b611c-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b611c-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b611c-117">Requirements</span></span>  
 <span data-ttu-id="b611c-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b611c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b611c-119">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="b611c-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b611c-120">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b611c-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b611c-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b611c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b611c-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b611c-122">See also</span></span>

- [<span data-ttu-id="b611c-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b611c-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)

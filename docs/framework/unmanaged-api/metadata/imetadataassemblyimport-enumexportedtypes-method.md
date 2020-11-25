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
ms.openlocfilehash: a8b2377c48331ff9f0e69876c51fb78c7190f694
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708896"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="b10a9-102">IMetaDataAssemblyImport::EnumExportedTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="b10a9-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>

<span data-ttu-id="b10a9-103">현재 메타 데이터 범위에서 어셈블리 매니페스트에 참조 된 내보낸 형식을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b10a9-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b10a9-104">구문</span><span class="sxs-lookup"><span data-stu-id="b10a9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b10a9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b10a9-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="b10a9-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b10a9-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b10a9-107">이 값은 메서드가 처음 호출 될 때 null 값 이어야 합니다 `EnumExportedTypes` .</span><span class="sxs-lookup"><span data-stu-id="b10a9-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="b10a9-108">제한이 `mdExportedType` 메타 데이터 토큰의 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="b10a9-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b10a9-109">진행 `mdExportedType` 배열에 배치할 수 있는 최대 토큰 수입니다 `rExportedTypes` .</span><span class="sxs-lookup"><span data-stu-id="b10a9-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b10a9-110">제한이 `mdExportedType` 에 실제로 배치 된 토큰의 수 `rExportedTypes` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b10a9-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b10a9-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="b10a9-111">Return Value</span></span>  
  
|<span data-ttu-id="b10a9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b10a9-112">HRESULT</span></span>|<span data-ttu-id="b10a9-113">설명</span><span class="sxs-lookup"><span data-stu-id="b10a9-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b10a9-114">`EnumExportedTypes` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b10a9-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b10a9-115">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b10a9-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="b10a9-116">이 경우 `pcTokens` 는 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b10a9-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b10a9-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b10a9-117">Requirements</span></span>  

 <span data-ttu-id="b10a9-118">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b10a9-118">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b10a9-119">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="b10a9-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b10a9-120">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b10a9-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b10a9-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b10a9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b10a9-122">참조</span><span class="sxs-lookup"><span data-stu-id="b10a9-122">See also</span></span>

- [<span data-ttu-id="b10a9-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b10a9-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)

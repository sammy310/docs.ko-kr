---
description: IMetaDataAssemblyEmit::D efineExportedType 메서드에 대해 자세히 알아보세요.
title: IMetaDataAssemblyEmit::DefineExportedType 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
ms.openlocfilehash: 0da1b1eb0880b0ba9df0ba9ad70b460163dffc39
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671115"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="d262e-103">IMetaDataAssemblyEmit::DefineExportedType 메서드</span><span class="sxs-lookup"><span data-stu-id="d262e-103">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>

<span data-ttu-id="d262e-104">지정된 내보낸 형식에 대한 메타데이터를 포함하는 `ExportedType` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d262e-104">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d262e-105">구문</span><span class="sxs-lookup"><span data-stu-id="d262e-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d262e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d262e-106">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="d262e-107">진행 내보낼 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d262e-107">[in] The name of type to be exported.</span></span> <span data-ttu-id="d262e-108">공용 언어 런타임의 버전 1.1의 경우 내보낸 형식의 이름은 형식에 대해에 지정 된 이름과 정확히 일치 해야 합니다 `TypeDef` .</span><span class="sxs-lookup"><span data-stu-id="d262e-108">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="d262e-109">진행 내보낸 형식이 구현 되는 위치를 지정 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d262e-109">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="d262e-110">유효한 값과 관련 의미는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d262e-110">The valid values and their associated meanings are:</span></span>  
  
- <span data-ttu-id="d262e-111">`mdFile` 형식이이 어셈블리 내의 다른 파일에 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d262e-111">`mdFile` The type is implemented in a different file within this assembly.</span></span>  
  
- <span data-ttu-id="d262e-112">`mdAssemblyRef` 형식은 다른 어셈블리에서 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d262e-112">`mdAssemblyRef` The type is implemented in a different assembly.</span></span>  
  
- <span data-ttu-id="d262e-113">`mdExportedTYpe` 형식은 다른 형식 내에 중첩 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d262e-113">`mdExportedTYpe` The type is nested within some other type.</span></span>  
  
- <span data-ttu-id="d262e-114">`mdFileNil` 형식이 매니페스트와 동일한 파일에 있고 중첩 형식이 아닌 경우</span><span class="sxs-lookup"><span data-stu-id="d262e-114">`mdFileNil` The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="d262e-115">진행 내보낼 형식을 지정 하는 메타 데이터에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d262e-115">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="d262e-116">이 값은 `TypeDef` 형식을 구현 하는 파일의 테이블에 입력 되며 해당 파일이이 어셈블리에 있는 경우에만 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d262e-116">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="d262e-117">진행 내보낸 형식에 대 한 속성 설정을 정의 하는 [Cortypeattr](cortypeattr-enumeration.md) 열거형 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="d262e-117">[in] A bitwise combination of [CorTypeAttr](cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="d262e-118">제한이 내보낸 형식을 나타내는 반환 된 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d262e-118">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d262e-119">설명</span><span class="sxs-lookup"><span data-stu-id="d262e-119">Remarks</span></span>  

 <span data-ttu-id="d262e-120">`ExportedType`메타 데이터 구조는이 어셈블리에 의해 노출 되는 각 형식에 대해 정의 되어야 하며 매니페스트를 포함 하 고 있지 않은 다른 모듈에서 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d262e-120">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d262e-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d262e-121">Requirements</span></span>  

 <span data-ttu-id="d262e-122">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d262e-122">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d262e-123">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="d262e-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d262e-124">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d262e-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d262e-125">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d262e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d262e-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d262e-126">See also</span></span>

- [<span data-ttu-id="d262e-127">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d262e-127">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)

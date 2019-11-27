---
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
ms.openlocfilehash: 44f97ef498eb8e64c55fc86b9f290b9e088293f6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432074"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="5a2c7-102">IMetaDataAssemblyEmit::DefineExportedType 메서드</span><span class="sxs-lookup"><span data-stu-id="5a2c7-102">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>
<span data-ttu-id="5a2c7-103">지정된 내보낸 형식에 대한 메타데이터를 포함하는 `ExportedType` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2c7-103">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a2c7-104">구문</span><span class="sxs-lookup"><span data-stu-id="5a2c7-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a2c7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5a2c7-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="5a2c7-106">진행 내보낼 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5a2c7-106">[in] The name of type to be exported.</span></span> <span data-ttu-id="5a2c7-107">공용 언어 런타임의 1.1 버전의 경우 내보낸 형식의 이름은 해당 형식의 `TypeDef`에 지정 된 이름과 정확히 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2c7-107">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="5a2c7-108">진행 내보낸 형식이 구현 되는 위치를 지정 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5a2c7-108">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="5a2c7-109">유효한 값과 관련 의미는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5a2c7-109">The valid values and their associated meanings are:</span></span>  
  
- <span data-ttu-id="5a2c7-110">형식이이 어셈블리 내의 다른 파일에 구현 `mdFile` 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2c7-110">`mdFile` The type is implemented in a different file within this assembly.</span></span>  
  
- <span data-ttu-id="5a2c7-111">형식이 다른 어셈블리에서 구현 `mdAssemblyRef` 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2c7-111">`mdAssemblyRef` The type is implemented in a different assembly.</span></span>  
  
- <span data-ttu-id="5a2c7-112">형식이 다른 형식 내에 중첩 되어 `mdExportedTYpe` 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2c7-112">`mdExportedTYpe` The type is nested within some other type.</span></span>  
  
- <span data-ttu-id="5a2c7-113">형식이 매니페스트와 동일한 파일에 있고 중첩 형식이 아닌 `mdFileNil`입니다.</span><span class="sxs-lookup"><span data-stu-id="5a2c7-113">`mdFileNil` The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="5a2c7-114">진행 내보낼 형식을 지정 하는 메타 데이터에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5a2c7-114">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="5a2c7-115">이 값은 형식을 구현 하는 파일의 `TypeDef` 테이블에 입력 되며 해당 파일이이 어셈블리에 있는 경우에만 관련 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a2c7-115">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="5a2c7-116">진행 내보낸 형식에 대 한 속성 설정을 정의 하는 [Cortypeattr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) 열거형 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="5a2c7-116">[in] A bitwise combination of [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="5a2c7-117">제한이 내보낸 형식을 나타내는 반환 된 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5a2c7-117">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a2c7-118">설명</span><span class="sxs-lookup"><span data-stu-id="5a2c7-118">Remarks</span></span>  
 <span data-ttu-id="5a2c7-119">이 어셈블리에 의해 노출 되는 각 형식에 대해 `ExportedType` 메타 데이터 구조를 정의 하 고 매니페스트를 포함 하는 것 이외의 모듈에서 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2c7-119">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a2c7-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a2c7-120">Requirements</span></span>  
 <span data-ttu-id="5a2c7-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a2c7-121">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a2c7-122">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="5a2c7-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a2c7-123">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a2c7-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5a2c7-124">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a2c7-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a2c7-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="5a2c7-125">See also</span></span>

- [<span data-ttu-id="5a2c7-126">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a2c7-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)

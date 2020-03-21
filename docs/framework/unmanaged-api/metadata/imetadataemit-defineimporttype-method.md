---
title: IMetaDataEmit::DefineImportType 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
ms.openlocfilehash: 6825a5198976cc7ab2c04ebd6e782418dcf4a8f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177689"
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="845dd-102">IMetaDataEmit::DefineImportType 메서드</span><span class="sxs-lookup"><span data-stu-id="845dd-102">IMetaDataEmit::DefineImportType Method</span></span>
<span data-ttu-id="845dd-103">현재 범위 외부에 정의된 지정된 형식에 대한 참조를 만들고 해당 참조에 대한 토큰을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="845dd-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="845dd-104">구문</span><span class="sxs-lookup"><span data-stu-id="845dd-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineImportType (
    [in]  IMetaDataAssemblyImport  *pAssemImport,
    [in]  const void               *pbHashValue,
    [in]  ULONG                    cbHashValue,
    [in]  IMetaDataImport          *pImport,
    [in]  mdTypeDef                tdImport,
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,
    [out] mdTypeRef                *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="845dd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="845dd-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="845dd-106">【인】 대상 형식을 가져오는 어셈블리를 나타내는 [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="845dd-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="845dd-107">【인】 `pAssemImport`에서 지정한 어셈블리에 대한 해시가 포함된 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="845dd-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="845dd-108">[in] `pbHashValue` 배열의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="845dd-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="845dd-109">【인】 대상 형식을 가져오는 메타데이터 범위를 나타내는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="845dd-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="845dd-110">【인】 대상 `mdTypeDef` 유형을 지정하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="845dd-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="845dd-111">【인】 대상 형식을 가져오는 어셈블리를 나타내는 [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="845dd-111">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="845dd-112">【아웃】 형식 `mdTypeRef` 참조의 현재 범위에 정의된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="845dd-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="845dd-113">설명</span><span class="sxs-lookup"><span data-stu-id="845dd-113">Remarks</span></span>  
 <span data-ttu-id="845dd-114">[IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) 메서드를 호출하기 전에 메서드를 `DefineImportType` 사용하여 멤버의 상위 클래스 또는 상위 인터페이스에 대한 현재 범위에서 형식 참조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="845dd-114">Prior to calling the [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="845dd-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="845dd-115">Requirements</span></span>  
 <span data-ttu-id="845dd-116">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="845dd-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="845dd-117">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="845dd-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="845dd-118">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="845dd-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="845dd-119">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="845dd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="845dd-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="845dd-120">See also</span></span>

- [<span data-ttu-id="845dd-121">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="845dd-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="845dd-122">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="845dd-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

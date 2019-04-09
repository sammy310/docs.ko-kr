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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9debf041a26af128dea3cde214630f5a95eac71
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090663"
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="7fad0-102">IMetaDataEmit::DefineImportType 메서드</span><span class="sxs-lookup"><span data-stu-id="7fad0-102">IMetaDataEmit::DefineImportType Method</span></span>
<span data-ttu-id="7fad0-103">현재 범위를 벗어난 정의 되 고 해당 참조에 대 한 토큰을 정의 하는 지정된 된 형식에 대 한 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7fad0-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fad0-104">구문</span><span class="sxs-lookup"><span data-stu-id="7fad0-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="7fad0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7fad0-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="7fad0-106">[in] [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 대상 형식의 가져온 어셈블리를 나타내는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="7fad0-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="7fad0-107">[in] 에 지정 된 어셈블리에 대 한 해시를 포함 하는 배열을 `pAssemImport`합니다.</span><span class="sxs-lookup"><span data-stu-id="7fad0-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="7fad0-108">[in] `pbHashValue` 배열의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7fad0-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="7fad0-109">[in] [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 대상 형식의 가져온 메타 데이터 범위를 나타내는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="7fad0-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="7fad0-110">[in] `mdTypeDef` 대상 형식을 지정 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7fad0-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="7fad0-111">[in] [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) 대상 유형을 가져올 어셈블리를 나타내는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="7fad0-111">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="7fad0-112">[out] `mdTypeRef` 형식 참조에 대 한 현재 범위에 정의 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7fad0-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7fad0-113">설명</span><span class="sxs-lookup"><span data-stu-id="7fad0-113">Remarks</span></span>  
 <span data-ttu-id="7fad0-114">호출 하기 전에 합니다 [imetadataemit:: Defineimportmember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) 메서드를 사용할 수는 `DefineImportType` 메서드를 현재 범위를 멤버의 부모 클래스 또는 부모 인터페이스의 형식 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7fad0-114">Prior to calling the [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fad0-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7fad0-115">Requirements</span></span>  
 <span data-ttu-id="7fad0-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7fad0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fad0-117">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7fad0-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7fad0-118">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="7fad0-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="7fad0-119">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="7fad0-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7fad0-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="7fad0-120">See also</span></span>

- [<span data-ttu-id="7fad0-121">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7fad0-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7fad0-122">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7fad0-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

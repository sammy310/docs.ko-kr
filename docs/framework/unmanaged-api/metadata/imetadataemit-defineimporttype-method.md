---
description: IMetaDataEmit::D efineImportType 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 7afe0fe400e4eb6e177a06e00b2d69202820804c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753434"
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="ce434-103">IMetaDataEmit::DefineImportType 메서드</span><span class="sxs-lookup"><span data-stu-id="ce434-103">IMetaDataEmit::DefineImportType Method</span></span>

<span data-ttu-id="ce434-104">현재 범위 외부에 정의 된 지정 된 형식에 대 한 참조를 만들고 해당 참조에 대 한 토큰을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce434-104">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce434-105">구문</span><span class="sxs-lookup"><span data-stu-id="ce434-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ce434-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ce434-106">Parameters</span></span>  

 `pAssemImport`  
 <span data-ttu-id="ce434-107">진행 대상 유형을 가져올 어셈블리를 나타내는 [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ce434-107">[in] An [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="ce434-108">진행 에 지정 된 어셈블리에 대 한 해시를 포함 하는 배열입니다 `pAssemImport` .</span><span class="sxs-lookup"><span data-stu-id="ce434-108">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="ce434-109">[in] `pbHashValue` 배열의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ce434-109">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="ce434-110">진행 대상 유형을 가져올 메타 데이터 범위를 나타내는 [IMetaDataImport](imetadataimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ce434-110">[in] An [IMetaDataImport](imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="ce434-111">진행 `mdTypeDef` 대상 형식을 지정 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ce434-111">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="ce434-112">진행 대상 형식을 가져오는 대상 어셈블리를 나타내는 [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ce434-112">[in] An [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="ce434-113">제한이 `mdTypeRef` 형식 참조에 대 한 현재 범위에서 정의 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ce434-113">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce434-114">설명</span><span class="sxs-lookup"><span data-stu-id="ce434-114">Remarks</span></span>  

 <span data-ttu-id="ce434-115">[IMetaDataEmit::D efineImportMember](imetadataemit-defineimportmember-method.md) 메서드를 호출 하기 전에 메서드를 사용 하 여 `DefineImportType` 현재 범위에서 멤버의 부모 클래스 또는 부모 인터페이스에 대 한 형식 참조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce434-115">Prior to calling the [IMetaDataEmit::DefineImportMember](imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce434-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce434-116">Requirements</span></span>  

 <span data-ttu-id="ce434-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce434-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce434-118">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="ce434-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce434-119">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce434-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce434-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce434-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce434-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce434-121">See also</span></span>

- [<span data-ttu-id="ce434-122">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce434-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ce434-123">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce434-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

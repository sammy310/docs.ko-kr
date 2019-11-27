---
title: IMetaDataAssemblyEmit::SetExportedTypeProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type:
- apiref
ms.openlocfilehash: ae682c354a7a5188611b103008a3e18f8d821260
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431935"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="90512-102">IMetaDataAssemblyEmit::SetExportedTypeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="90512-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="90512-103">지정된 `ExportedType` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="90512-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90512-104">구문</span><span class="sxs-lookup"><span data-stu-id="90512-104">Syntax</span></span>  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90512-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="90512-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="90512-106">진행 수정할 `ExportedType` 메타 데이터 구조를 지정 하는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="90512-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="90512-107">진행 이 형식을 구현 하는 방법을 지정 하는 `File`, `AssemblyRef`또는 `ExportedType`형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="90512-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="90512-108">진행 코드 파일에서 참조 되는 `TypeDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="90512-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="90512-109">진행 형식의 특성을 지정 하는 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="90512-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90512-110">주의</span><span class="sxs-lookup"><span data-stu-id="90512-110">Remarks</span></span>  
 <span data-ttu-id="90512-111">`ExportedType` 메타 데이터 구조를 만들려면 [IMetaDataAssemblyEmit::D efineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="90512-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90512-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="90512-112">Requirements</span></span>  
 <span data-ttu-id="90512-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="90512-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90512-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="90512-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90512-115">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90512-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="90512-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90512-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90512-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90512-117">See also</span></span>

- [<span data-ttu-id="90512-118">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90512-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)

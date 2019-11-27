---
title: IMetaDataAssemblyImport::FindExportedTypeByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
ms.openlocfilehash: 3e470250fa0e86610fcc9a6d6e2ca03569d62b54
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449453"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="0556f-102">IMetaDataAssemblyImport::FindExportedTypeByName 메서드</span><span class="sxs-lookup"><span data-stu-id="0556f-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="0556f-103">이름 및 바깥쪽 형식이 지정 된 경우 내보낸 형식에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0556f-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0556f-104">구문</span><span class="sxs-lookup"><span data-stu-id="0556f-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0556f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0556f-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="0556f-106">진행 내보낸 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0556f-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="0556f-107">진행 내보낸 형식의 바깥쪽 클래스에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0556f-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="0556f-108">이 값은 요청 된 내보낸 형식이 중첩 형식이 아닌 경우에 `mdExportedTypeNil` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0556f-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="0556f-109">제한이 내보낸 형식을 나타내는 `mdExportedType` 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0556f-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0556f-110">주의</span><span class="sxs-lookup"><span data-stu-id="0556f-110">Remarks</span></span>  
 <span data-ttu-id="0556f-111">`FindExportedTypeByName` 메서드는 참조를 확인 하기 위해 공용 언어 런타임에서 사용 하는 표준 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0556f-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0556f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0556f-112">Requirements</span></span>  
 <span data-ttu-id="0556f-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0556f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0556f-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="0556f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0556f-115">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0556f-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0556f-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0556f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0556f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0556f-117">See also</span></span>

- [<span data-ttu-id="0556f-118">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0556f-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="0556f-119">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="0556f-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)

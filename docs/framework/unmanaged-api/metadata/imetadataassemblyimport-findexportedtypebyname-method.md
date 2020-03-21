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
ms.openlocfilehash: edfe5de9c9d7ef9607a2eea5146194bbd4393a92
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175995"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="0b340-102">IMetaDataAssemblyImport::FindExportedTypeByName 메서드</span><span class="sxs-lookup"><span data-stu-id="0b340-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="0b340-103">이름과 둘러싸는 형식이 지정된 내보낸 형식에 대한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0b340-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b340-104">구문</span><span class="sxs-lookup"><span data-stu-id="0b340-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b340-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0b340-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="0b340-106">【인】 내보낸 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0b340-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="0b340-107">【인】 내보낸 형식의 둘러싸는 클래스에 대한 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0b340-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="0b340-108">이 값은 `mdExportedTypeNil` 요청된 내보낸 형식이 중첩 형식이 아닌 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="0b340-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="0b340-109">【아웃】 내보낸 형식을 `mdExportedType` 나타내는 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0b340-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b340-110">설명</span><span class="sxs-lookup"><span data-stu-id="0b340-110">Remarks</span></span>  
 <span data-ttu-id="0b340-111">이 `FindExportedTypeByName` 메서드는 참조를 해결하기 위해 공통 언어 런타임에서 사용하는 표준 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b340-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b340-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0b340-112">Requirements</span></span>  
 <span data-ttu-id="0b340-113">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b340-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b340-114">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="0b340-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0b340-115">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="0b340-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0b340-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b340-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b340-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b340-117">See also</span></span>

- [<span data-ttu-id="0b340-118">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0b340-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="0b340-119">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="0b340-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)

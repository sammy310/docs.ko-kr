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
ms.openlocfilehash: b1672d98d76241e5af4b6b60a38785f1278e15a8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731594"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="6fb35-102">IMetaDataAssemblyImport::FindExportedTypeByName 메서드</span><span class="sxs-lookup"><span data-stu-id="6fb35-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>

<span data-ttu-id="6fb35-103">이름 및 바깥쪽 형식이 지정 된 경우 내보낸 형식에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6fb35-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fb35-104">구문</span><span class="sxs-lookup"><span data-stu-id="6fb35-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fb35-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6fb35-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="6fb35-106">진행 내보낸 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb35-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="6fb35-107">진행 내보낸 형식의 바깥쪽 클래스에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb35-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="6fb35-108">`mdExportedTypeNil`요청 된 내보낸 형식이 중첩 형식이 아닌 경우이 값은입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb35-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="6fb35-109">제한이 내보낸 형식을 나타내는 토큰에 대 한 포인터입니다 `mdExportedType` .</span><span class="sxs-lookup"><span data-stu-id="6fb35-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fb35-110">설명</span><span class="sxs-lookup"><span data-stu-id="6fb35-110">Remarks</span></span>  

 <span data-ttu-id="6fb35-111">`FindExportedTypeByName`메서드는 참조를 확인 하기 위해 공용 언어 런타임에서 사용 하는 표준 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb35-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fb35-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6fb35-112">Requirements</span></span>  

 <span data-ttu-id="6fb35-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fb35-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fb35-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="6fb35-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6fb35-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fb35-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6fb35-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fb35-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fb35-117">참조</span><span class="sxs-lookup"><span data-stu-id="6fb35-117">See also</span></span>

- [<span data-ttu-id="6fb35-118">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6fb35-118">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="6fb35-119">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="6fb35-119">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)

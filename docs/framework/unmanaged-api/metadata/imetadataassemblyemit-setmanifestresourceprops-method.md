---
title: IMetaDataAssemblyEmit::SetManifestResourceProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetManifestResourceProps
helpviewer_keywords:
- SetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetManifestResourceProps method [.NET Framework metadata]
ms.assetid: ef77efd1-849c-4e51-ba92-7ee3d2bf0339
topic_type:
- apiref
ms.openlocfilehash: 9370b27fd385b0223b354365d64aa57048f4ec69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177837"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="60ca6-102">IMetaDataAssemblyEmit::SetManifestResourceProps 메서드</span><span class="sxs-lookup"><span data-stu-id="60ca6-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="60ca6-103">지정된 `ManifestResource` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="60ca6-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60ca6-104">구문</span><span class="sxs-lookup"><span data-stu-id="60ca6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60ca6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="60ca6-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="60ca6-106">【인】 수정할 `ManifestResource` 메타데이터 구조를 지정하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="60ca6-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="60ca6-107">【인】 리소스 공급자에 `File` 매핑되는 토큰 또는 `AssemblyRef`의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="60ca6-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="60ca6-108">【인】 파일 내의 리소스의 시작 부분에 대한 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="60ca6-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="60ca6-109">【인】 리소스의 특성을 지정하는 플래그 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="60ca6-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60ca6-110">설명</span><span class="sxs-lookup"><span data-stu-id="60ca6-110">Remarks</span></span>  
 <span data-ttu-id="60ca6-111">`ManifestResource` 메타데이터 구조를 만들려면 [IMetaDataAssemblyEmit::DefineManifestResource 메서드를](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="60ca6-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60ca6-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="60ca6-112">Requirements</span></span>  
 <span data-ttu-id="60ca6-113">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60ca6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60ca6-114">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="60ca6-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="60ca6-115">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="60ca6-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="60ca6-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60ca6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60ca6-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60ca6-117">See also</span></span>

- [<span data-ttu-id="60ca6-118">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60ca6-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)

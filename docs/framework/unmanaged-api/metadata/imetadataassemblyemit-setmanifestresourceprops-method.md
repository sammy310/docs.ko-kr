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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d080a3077df2cb4ad57ef463b5e02a3a28d8429d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779405"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="34495-102">IMetaDataAssemblyEmit::SetManifestResourceProps 메서드</span><span class="sxs-lookup"><span data-stu-id="34495-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="34495-103">지정된 `ManifestResource` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="34495-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34495-104">구문</span><span class="sxs-lookup"><span data-stu-id="34495-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34495-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="34495-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="34495-106">[in] 지정 하는 토큰을 `ManifestResource` 수정할 메타 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="34495-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="34495-107">[in] 형식의 토큰 `File` 또는 `AssemblyRef`, 리소스 공급자에 매핑되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="34495-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="34495-108">[in] 파일 내에서 리소스의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="34495-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="34495-109">[in] 리소스의 특성을 지정 하는 플래그 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="34495-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34495-110">설명</span><span class="sxs-lookup"><span data-stu-id="34495-110">Remarks</span></span>  
 <span data-ttu-id="34495-111">만들려는 `ManifestResource` 메타 데이터 구조를 사용 합니다 [imetadataassemblyemit:: Definemanifestresource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="34495-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34495-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="34495-112">Requirements</span></span>  
 <span data-ttu-id="34495-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="34495-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34495-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="34495-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="34495-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="34495-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="34495-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34495-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34495-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="34495-117">See also</span></span>

- [<span data-ttu-id="34495-118">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="34495-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)

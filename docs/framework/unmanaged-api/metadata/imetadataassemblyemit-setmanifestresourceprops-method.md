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
ms.openlocfilehash: f6b5e12df60663b75e10b04eaa008a75d720d753
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434434"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="3e97a-102">IMetaDataAssemblyEmit::SetManifestResourceProps 메서드</span><span class="sxs-lookup"><span data-stu-id="3e97a-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="3e97a-103">지정된 `ManifestResource` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e97a-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e97a-104">구문</span><span class="sxs-lookup"><span data-stu-id="3e97a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e97a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3e97a-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="3e97a-106">진행 수정할 `ManifestResource` 메타 데이터 구조를 지정 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3e97a-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="3e97a-107">진행 리소스 공급자에 매핑되는 `File` 또는 `AssemblyRef`형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3e97a-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="3e97a-108">진행 파일 내 리소스의 시작에 대 한 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="3e97a-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="3e97a-109">진행 리소스의 특성을 지정 하는 플래그 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="3e97a-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e97a-110">주의</span><span class="sxs-lookup"><span data-stu-id="3e97a-110">Remarks</span></span>  
 <span data-ttu-id="3e97a-111">`ManifestResource` 메타 데이터 구조를 만들려면 [IMetaDataAssemblyEmit::D efinemanifestresource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e97a-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e97a-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e97a-112">Requirements</span></span>  
 <span data-ttu-id="3e97a-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e97a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e97a-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="3e97a-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3e97a-115">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e97a-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3e97a-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e97a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e97a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e97a-117">See also</span></span>

- [<span data-ttu-id="3e97a-118">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e97a-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)

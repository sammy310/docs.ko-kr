---
description: '자세히 알아보기: IMetaDataAssemblyEmit:: SetManifestResourceProps 메서드'
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
ms.openlocfilehash: 0d5022c4acc562f9e77cec4ba080815db410862b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721028"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="02120-103">IMetaDataAssemblyEmit::SetManifestResourceProps 메서드</span><span class="sxs-lookup"><span data-stu-id="02120-103">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>

<span data-ttu-id="02120-104">지정된 `ManifestResource` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="02120-104">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02120-105">구문</span><span class="sxs-lookup"><span data-stu-id="02120-105">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02120-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02120-106">Parameters</span></span>  

 `mr`  
 <span data-ttu-id="02120-107">진행 수정할 메타 데이터 구조를 지정 하는 토큰입니다 `ManifestResource` .</span><span class="sxs-lookup"><span data-stu-id="02120-107">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="02120-108">진행 `File` `AssemblyRef` 리소스 공급자에 매핑되는 또는 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="02120-108">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="02120-109">진행 파일 내 리소스의 시작에 대 한 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="02120-109">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="02120-110">진행 리소스의 특성을 지정 하는 플래그 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="02120-110">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02120-111">설명</span><span class="sxs-lookup"><span data-stu-id="02120-111">Remarks</span></span>  

 <span data-ttu-id="02120-112">`ManifestResource`메타 데이터 구조를 만들려면 [IMetaDataAssemblyEmit::D efinemanifestresource](imetadataassemblyemit-definemanifestresource-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="02120-112">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02120-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02120-113">Requirements</span></span>  

 <span data-ttu-id="02120-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02120-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02120-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="02120-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="02120-116">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02120-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="02120-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02120-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02120-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02120-118">See also</span></span>

- [<span data-ttu-id="02120-119">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02120-119">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)

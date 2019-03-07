---
title: IMetaDataImport::ResolveTypeRef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4f74952c2b3960dc29e0d1970276d972b048837f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499162"
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="5c4c4-102">IMetaDataImport::ResolveTypeRef 메서드</span><span class="sxs-lookup"><span data-stu-id="5c4c4-102">IMetaDataImport::ResolveTypeRef Method</span></span>
<span data-ttu-id="5c4c4-103">확인을 <xref:System.Type> 지정한 TypeRef 토큰이 나타내는 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c4c4-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c4c4-104">구문</span><span class="sxs-lookup"><span data-stu-id="5c4c4-104">Syntax</span></span>  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c4c4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5c4c4-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="5c4c4-106">[in] 에 대 한 참조 된 형식 정보를 반환 하는 TypeRef 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5c4c4-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="5c4c4-107">[in] 반환할 인터페이스의 IID `ppIScope`합니다.</span><span class="sxs-lookup"><span data-stu-id="5c4c4-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="5c4c4-108">일반적으로이 IID_IMetaDataImport 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5c4c4-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="5c4c4-109">[out] 인터페이스 참조 형식이 정의 되어 있는 모듈 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="5c4c4-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="5c4c4-110">[out] 참조 된 형식을 나타내는 TypeDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5c4c4-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c4c4-111">설명</span><span class="sxs-lookup"><span data-stu-id="5c4c4-111">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5c4c4-112">여러 응용 프로그램 도메인이 로드 된 경우에이 메서드를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5c4c4-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="5c4c4-113">메서드는 응용 프로그램 도메인 경계를 고려 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5c4c4-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="5c4c4-114">여러 버전의 어셈블리가 로드 되 고 동일한 네임 스페이스를 사용 하 여 동일한 형식 포함을 하는 경우 메서드를 찾으면 첫 번째 유형은 모듈 범위를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c4c4-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="5c4c4-115">`ResolveTypeRef` 메서드는 다른 모듈에서 형식 정의 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c4c4-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="5c4c4-116">형식 정의 있으면 `ResolveTypeRef` 인터페이스 형식에 대 한 TypeDef 토큰 뿐만 아니라 해당 모듈 범위를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c4c4-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="5c4c4-117">형식 참조를 해결 해야 할 해결 범위가 AssemblyRef를 하는 경우는 `ResolveTypeRef` 메서드 중 하나를 호출 하 여 이미 열려 있는 메타 데이터 범위에만 일치 항목을 검색 합니다 [imetadatadispenser:: Openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)메서드 또는 [imetadatadispenser:: Openscopeonmemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="5c4c4-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="5c4c4-118">왜냐하면 `ResolveTypeRef` AssemblyRef 범위만 디스크 또는 전역 어셈블리 캐시에 어셈블리 저장 위치에서 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5c4c4-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c4c4-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c4c4-119">Requirements</span></span>  
 <span data-ttu-id="5c4c4-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5c4c4-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c4c4-121">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5c4c4-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c4c4-122">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5c4c4-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c4c4-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c4c4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c4c4-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="5c4c4-124">See also</span></span>
- [<span data-ttu-id="5c4c4-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c4c4-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5c4c4-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c4c4-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

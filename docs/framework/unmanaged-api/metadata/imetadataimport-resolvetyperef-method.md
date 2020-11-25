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
ms.openlocfilehash: 76c5519a6cd1b8994e2f869281f13d8269e89fde
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702825"
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="950c6-102">IMetaDataImport::ResolveTypeRef 메서드</span><span class="sxs-lookup"><span data-stu-id="950c6-102">IMetaDataImport::ResolveTypeRef Method</span></span>

<span data-ttu-id="950c6-103">지정 된 <xref:System.Type> TypeRef 토큰이 나타내는 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="950c6-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="950c6-104">구문</span><span class="sxs-lookup"><span data-stu-id="950c6-104">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="950c6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="950c6-105">Parameters</span></span>  

 `tr`  
 <span data-ttu-id="950c6-106">진행 참조 된 형식 정보를 반환할 TypeRef 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="950c6-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="950c6-107">진행 에서 반환할 인터페이스의 IID입니다 `ppIScope` .</span><span class="sxs-lookup"><span data-stu-id="950c6-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="950c6-108">일반적으로 IID_IMetaDataImport 합니다.</span><span class="sxs-lookup"><span data-stu-id="950c6-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="950c6-109">제한이 참조 된 형식이 정의 된 모듈 범위에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="950c6-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="950c6-110">제한이 참조 된 형식을 나타내는 TypeDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="950c6-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="950c6-111">설명</span><span class="sxs-lookup"><span data-stu-id="950c6-111">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="950c6-112">여러 응용 프로그램 도메인을 로드 하는 경우에는이 메서드를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="950c6-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="950c6-113">이 메서드는 응용 프로그램 도메인 경계를 고려 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="950c6-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="950c6-114">어셈블리의 여러 버전이 로드 되 고 동일한 네임 스페이스를 가진 동일한 형식을 포함 하는 경우 메서드는 찾은 첫 번째 형식의 모듈 범위를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="950c6-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="950c6-115">`ResolveTypeRef`메서드는 다른 모듈의 형식 정의를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="950c6-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="950c6-116">형식 정의가 있으면에서 `ResolveTypeRef` 해당 모듈 범위에 대 한 인터페이스와 형식에 대 한 TypeDef 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="950c6-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="950c6-117">확인할 형식 참조의 확인 범위가 AssemblyRef 인 경우 `ResolveTypeRef` 메서드는 [IMetaDataDispenser:: openscope](imetadatadispenser-openscope-method.md) 메서드 또는 [IMetaDataDispenser:: OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) 메서드를 호출 하 여 이미 열려 있는 메타 데이터 범위 에서만 일치 하는 항목을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="950c6-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="950c6-118">이는 `ResolveTypeRef` 에서 디스크 또는 전역 어셈블리 캐시에서 어셈블리가 저장 된 AssemblyRef 범위만 확인할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="950c6-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="950c6-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="950c6-119">Requirements</span></span>  

 <span data-ttu-id="950c6-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="950c6-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="950c6-121">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="950c6-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="950c6-122">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="950c6-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="950c6-123">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="950c6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="950c6-124">참조</span><span class="sxs-lookup"><span data-stu-id="950c6-124">See also</span></span>

- [<span data-ttu-id="950c6-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="950c6-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="950c6-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="950c6-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

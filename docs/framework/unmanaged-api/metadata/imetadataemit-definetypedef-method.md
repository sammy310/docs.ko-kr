---
title: IMetaDataEmit::DefineTypeDef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
ms.openlocfilehash: dc064b00e32bb6b1d8c2d0c20f571b35919eae23
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009342"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="5aced-102">IMetaDataEmit::DefineTypeDef 메서드</span><span class="sxs-lookup"><span data-stu-id="5aced-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="5aced-103">공용 언어 런타임 형식에 대 한 형식 정의를 만들고 해당 형식 정의에 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5aced-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5aced-104">구문</span><span class="sxs-lookup"><span data-stu-id="5aced-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5aced-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5aced-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="5aced-106">진행 유니코드 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5aced-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="5aced-107">[in] `TypeDef` 특성.</span><span class="sxs-lookup"><span data-stu-id="5aced-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="5aced-108">값의 비트 마스크입니다 `CoreTypeAttr` .</span><span class="sxs-lookup"><span data-stu-id="5aced-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="5aced-109">진행 기본 클래스의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5aced-109">[in] The token of the base class.</span></span> <span data-ttu-id="5aced-110">`mdTypeDef`또는 토큰 이어야 합니다 `mdTypeRef` .</span><span class="sxs-lookup"><span data-stu-id="5aced-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="5aced-111">진행 이 클래스 또는 인터페이스가 구현 하는 인터페이스를 지정 하는 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5aced-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="5aced-112">제한이 `mdTypeDef`할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5aced-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5aced-113">설명</span><span class="sxs-lookup"><span data-stu-id="5aced-113">Remarks</span></span>  
 <span data-ttu-id="5aced-114">의 플래그는 `dwTypeDefFlags` 만들려는 형식이 공용 형식 시스템 참조 형식 (클래스 또는 인터페이스) 인지 아니면 공용 형식 시스템 값 형식 인지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aced-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="5aced-115">제공 된 매개 변수에 따라이 메서드는 `mdInterfaceImpl` 이 형식에 의해 상속 되거나 구현 되는 각 인터페이스에 대 한 레코드를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5aced-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="5aced-116">그러나이 메서드는 이러한 토큰을 반환 하지 않습니다 `mdInterfaceImpl` .</span><span class="sxs-lookup"><span data-stu-id="5aced-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="5aced-117">클라이언트는 나중에 토큰을 추가 하거나 수정 하려는 경우 `mdInterfaceImpl` 인터페이스를 사용 하 여이를 열거 해야 합니다 `IMetaDataImport` .</span><span class="sxs-lookup"><span data-stu-id="5aced-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="5aced-118">인터페이스의 COM 의미 체계를 사용 하려면 `[default]` 기본 인터페이스를의 첫 번째 요소로 지정 해야 합니다 `rtkImplements` . 클래스에 설정 된 사용자 지정 특성은 클래스에 기본 인터페이스가 있음을 나타내며이는 항상 `mdInterfaceImpl` 클래스에 대해 선언 된 첫 번째 토큰으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5aced-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="5aced-119">배열의 각 요소 `rtkImplements` 는 `mdTypeDef` 또는 토큰을 보유 `mdTypeRef` 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aced-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="5aced-120">배열의 마지막 요소는 이어야 합니다 `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="5aced-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5aced-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5aced-121">Requirements</span></span>  
 <span data-ttu-id="5aced-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5aced-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5aced-123">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="5aced-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5aced-124">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5aced-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5aced-125">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5aced-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aced-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5aced-126">See also</span></span>

- [<span data-ttu-id="5aced-127">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5aced-127">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="5aced-128">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5aced-128">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

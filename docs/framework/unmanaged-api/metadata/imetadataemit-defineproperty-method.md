---
title: IMetaDataEmit::DefineProperty 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
ms.openlocfilehash: d2a4a15126f34666a58021a59e9e193685b15a49
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719491"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="f7086-102">IMetaDataEmit::DefineProperty 메서드</span><span class="sxs-lookup"><span data-stu-id="f7086-102">IMetaDataEmit::DefineProperty Method</span></span>

<span data-ttu-id="f7086-103">지정 된 및 메서드 접근자를 사용 하 여 지정 된 형식에 대 한 속성 정의를 만들고 `get` `set` 해당 속성 정의에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f7086-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7086-104">구문</span><span class="sxs-lookup"><span data-stu-id="f7086-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineProperty (
    [in]  mdTypeDef          td,
    [in]  LPCWSTR            szProperty,
    [in]  DWORD              dwPropFlags,
    [in]  PCCOR_SIGNATURE    pvSig,
    [in]  ULONG              cbSig,
    [in]  DWORD              dwCPlusTypeFlag,
    [in]  void const         *pValue,
    [in]  ULONG              cchValue,
    [in]  mdMethodDef        mdSetter,
    [in]  mdMethodDef        mdGetter,
    [in]  mdMethodDef        rmdOtherMethods[],
    [out] mdProperty         *pmdProp
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7086-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f7086-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="f7086-106">진행 속성이 정의 되는 클래스 또는 인터페이스에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f7086-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="f7086-107">진행 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f7086-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="f7086-108">진행 속성 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="f7086-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="f7086-109">진행 속성 시그니처입니다.</span><span class="sxs-lookup"><span data-stu-id="f7086-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="f7086-110">진행 의 바이트 수 `pvSig` 입니다.</span><span class="sxs-lookup"><span data-stu-id="f7086-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="f7086-111">진행 속성의 기본값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f7086-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="f7086-112">진행 속성의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="f7086-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="f7086-113">진행 의 (유니코드) 문자 수입니다 `pValue` .</span><span class="sxs-lookup"><span data-stu-id="f7086-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="f7086-114">진행 속성 값을 설정 하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="f7086-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="f7086-115">진행 속성 값을 가져오는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="f7086-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="f7086-116">진행 속성과 연결 된 다른 메서드의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f7086-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="f7086-117">을 사용 하 여 배열을 종료 `mdTokenNil` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7086-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="f7086-118">제한이 `mdProperty` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f7086-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7086-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7086-119">Requirements</span></span>  

 <span data-ttu-id="f7086-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7086-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7086-121">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="f7086-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f7086-122">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7086-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7086-123">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7086-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7086-124">참조</span><span class="sxs-lookup"><span data-stu-id="f7086-124">See also</span></span>

- [<span data-ttu-id="f7086-125">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f7086-125">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f7086-126">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f7086-126">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

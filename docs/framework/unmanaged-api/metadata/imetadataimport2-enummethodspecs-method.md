---
title: IMetaDataImport2::EnumMethodSpecs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
ms.openlocfilehash: 4a1de144163ec2b4952bd16b59fb1c92b706631b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428304"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="2213d-102">IMetaDataImport2::EnumMethodSpecs 메서드</span><span class="sxs-lookup"><span data-stu-id="2213d-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="2213d-103">지정 된 MethodDef 또는 MemberRef 토큰과 연결 된 MethodSpec 토큰 배열의 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2213d-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2213d-104">구문</span><span class="sxs-lookup"><span data-stu-id="2213d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="2213d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2213d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2213d-106">[in, out] `rMethodSpecs`열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2213d-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="2213d-107">진행 MethodSpec 토큰이 열거 될 메서드를 나타내는 MemberRef 또는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2213d-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="2213d-108">`tk`의 값이 0 이면 범위에 있는 모든 MethodSpec 토큰이 열거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2213d-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="2213d-109">제한이 열거할 MethodSpec 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="2213d-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2213d-110">진행 `rMethodSpecs`에 저장할 요청 된 최대 토큰 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2213d-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="2213d-111">제한이 `rMethodSpecs`에 배치 된 반환 된 토큰 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2213d-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2213d-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="2213d-112">Return Value</span></span>  
  
|<span data-ttu-id="2213d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2213d-113">HRESULT</span></span>|<span data-ttu-id="2213d-114">설명</span><span class="sxs-lookup"><span data-stu-id="2213d-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2213d-115">`EnumMethodSpecs` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2213d-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2213d-116">`phEnum`에는 멤버 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2213d-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="2213d-117">이 경우 `pcMethodSpecs`은 0 (영)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2213d-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2213d-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2213d-118">Requirements</span></span>  
 <span data-ttu-id="2213d-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2213d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2213d-120">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="2213d-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2213d-121">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2213d-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2213d-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2213d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2213d-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="2213d-123">See also</span></span>

- [<span data-ttu-id="2213d-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2213d-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="2213d-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2213d-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)

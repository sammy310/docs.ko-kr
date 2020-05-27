---
title: IMetaDataEmit::DefinePermissionSet 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePermissionSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type:
- apiref
ms.openlocfilehash: a069e2f4ec5d4114e9504fa5a58c5066fdfd7249
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008042"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="fabe5-102">IMetaDataEmit::DefinePermissionSet 메서드</span><span class="sxs-lookup"><span data-stu-id="fabe5-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="fabe5-103">지정 된 메타 데이터 시그니처를 사용 하 여 권한 집합에 대 한 정의를 만들고 해당 권한 집합 정의에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fabe5-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fabe5-104">구문</span><span class="sxs-lookup"><span data-stu-id="fabe5-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,
    [in]  DWORD          dwAction,
    [in]  void const     *pvPermission,
    [in]  ULONG          cbPermission,
    [out] mdPermission   *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fabe5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fabe5-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="fabe5-106">진행 데코레이팅 할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fabe5-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="fabe5-107">진행 사용할 선언적 보안의 형식을 지정 하는 [CorDeclSecurity](cordeclsecurity-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fabe5-107">[in] A [CorDeclSecurity](cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="fabe5-108">진행 권한 BLOB입니다.</span><span class="sxs-lookup"><span data-stu-id="fabe5-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="fabe5-109">진행 의 크기 (바이트)입니다 `pvPermission` .</span><span class="sxs-lookup"><span data-stu-id="fabe5-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="fabe5-110">제한이 반환 된 권한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="fabe5-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fabe5-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fabe5-111">Requirements</span></span>  
 <span data-ttu-id="fabe5-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fabe5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fabe5-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="fabe5-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fabe5-114">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fabe5-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fabe5-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fabe5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fabe5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fabe5-116">See also</span></span>

- [<span data-ttu-id="fabe5-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fabe5-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="fabe5-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fabe5-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

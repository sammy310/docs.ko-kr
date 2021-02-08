---
description: IMetaDataEmit::D efinePermissionSet 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: f5c3f1466217713cb3970c805079d8f65fd429c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784082"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="a45ce-103">IMetaDataEmit::DefinePermissionSet 메서드</span><span class="sxs-lookup"><span data-stu-id="a45ce-103">IMetaDataEmit::DefinePermissionSet Method</span></span>

<span data-ttu-id="a45ce-104">지정 된 메타 데이터 시그니처를 사용 하 여 권한 집합에 대 한 정의를 만들고 해당 권한 집합 정의에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-104">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a45ce-105">구문</span><span class="sxs-lookup"><span data-stu-id="a45ce-105">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,
    [in]  DWORD          dwAction,
    [in]  void const     *pvPermission,
    [in]  ULONG          cbPermission,
    [out] mdPermission   *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a45ce-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a45ce-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="a45ce-107">진행 데코레이팅 할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-107">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="a45ce-108">진행 사용할 선언적 보안의 형식을 지정 하는 [CorDeclSecurity](cordeclsecurity-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-108">[in] A [CorDeclSecurity](cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="a45ce-109">진행 권한 BLOB입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-109">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="a45ce-110">진행 의 크기 (바이트)입니다 `pvPermission` .</span><span class="sxs-lookup"><span data-stu-id="a45ce-110">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="a45ce-111">제한이 반환 된 권한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-111">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a45ce-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a45ce-112">Requirements</span></span>  

 <span data-ttu-id="a45ce-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a45ce-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a45ce-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="a45ce-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a45ce-115">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a45ce-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a45ce-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a45ce-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a45ce-117">See also</span></span>

- [<span data-ttu-id="a45ce-118">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a45ce-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="a45ce-119">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a45ce-119">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

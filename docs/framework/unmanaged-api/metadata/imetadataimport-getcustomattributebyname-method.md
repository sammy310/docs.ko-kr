---
title: IMetaDataImport::GetCustomAttributeByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
ms.openlocfilehash: bd7ba7ff10918e5953ea8ae89a60af3115af48a3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437691"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="ed11f-102">IMetaDataImport::GetCustomAttributeByName 메서드</span><span class="sxs-lookup"><span data-stu-id="ed11f-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>
<span data-ttu-id="ed11f-103">이름 및 소유자가 지정 된 경우 사용자 지정 특성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ed11f-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed11f-104">구문</span><span class="sxs-lookup"><span data-stu-id="ed11f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed11f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ed11f-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="ed11f-106">진행 사용자 지정 특성을 소유 하는 개체를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ed11f-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="ed11f-107">진행 사용자 지정 특성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ed11f-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="ed11f-108">제한이 사용자 지정 특성 값에 해당 하는 데이터 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ed11f-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="ed11f-109">제한이 \*`ppData`에서 반환 된 데이터의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="ed11f-109">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed11f-110">주의</span><span class="sxs-lookup"><span data-stu-id="ed11f-110">Remarks</span></span>  
 <span data-ttu-id="ed11f-111">동일한 소유자에 대해 여러 사용자 지정 특성을 정의 하는 것은 유효 합니다. 동일한 이름을 가진 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed11f-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="ed11f-112">그러나 `GetCustomAttributeByName`는 하나의 인스턴스만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed11f-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="ed11f-113">`GetCustomAttributeByName` 발견 한 첫 번째 인스턴스를 반환 합니다. 사용자 지정 특성의 모든 인스턴스를 찾으려면 [IMetaDataImport:: EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed11f-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed11f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed11f-114">Requirements</span></span>  
 <span data-ttu-id="ed11f-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed11f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed11f-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="ed11f-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed11f-117">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed11f-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ed11f-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed11f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed11f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed11f-119">See also</span></span>

- [<span data-ttu-id="ed11f-120">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed11f-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ed11f-121">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed11f-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

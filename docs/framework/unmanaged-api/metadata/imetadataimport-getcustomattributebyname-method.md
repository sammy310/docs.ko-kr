---
description: '자세히 알아보기: IMetaDataImport:: GetCustomAttributeByName 메서드'
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
ms.openlocfilehash: 1a9ca5f7fe13243c01c5dbcb9f49955e9ce05c26
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745491"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="2649d-103">IMetaDataImport::GetCustomAttributeByName 메서드</span><span class="sxs-lookup"><span data-stu-id="2649d-103">IMetaDataImport::GetCustomAttributeByName Method</span></span>

<span data-ttu-id="2649d-104">이름 및 소유자가 지정 된 경우 사용자 지정 특성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2649d-104">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2649d-105">구문</span><span class="sxs-lookup"><span data-stu-id="2649d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2649d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2649d-106">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="2649d-107">진행 사용자 지정 특성을 소유 하는 개체를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2649d-107">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="2649d-108">진행 사용자 지정 특성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2649d-108">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="2649d-109">제한이 사용자 지정 특성 값에 해당 하는 데이터 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2649d-109">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="2649d-110">제한이 \*에서 반환 된 데이터의 크기 (바이트)입니다 `ppData` .</span><span class="sxs-lookup"><span data-stu-id="2649d-110">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2649d-111">설명</span><span class="sxs-lookup"><span data-stu-id="2649d-111">Remarks</span></span>  

 <span data-ttu-id="2649d-112">동일한 소유자에 대해 여러 사용자 지정 특성을 정의 하는 것은 유효 합니다. 동일한 이름을 가진 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2649d-112">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="2649d-113">그러나는 `GetCustomAttributeByName` 인스턴스를 하나만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2649d-113">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="2649d-114">`GetCustomAttributeByName`는 발견 된 첫 번째 인스턴스를 반환 합니다. 사용자 지정 특성의 모든 인스턴스를 찾으려면 [IMetaDataImport:: EnumCustomAttributes](imetadataimport-enumcustomattributes-method.md) 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2649d-114">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2649d-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2649d-115">Requirements</span></span>  

 <span data-ttu-id="2649d-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2649d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2649d-117">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="2649d-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2649d-118">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2649d-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2649d-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2649d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2649d-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2649d-120">See also</span></span>

- [<span data-ttu-id="2649d-121">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2649d-121">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="2649d-122">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2649d-122">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

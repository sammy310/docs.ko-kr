---
title: IMetaDataConverter::GetTypeLibFromMetaData 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
ms.openlocfilehash: eed8661f8885ca16492ab336a599b5290057843a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714603"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="765cc-102">IMetaDataConverter::GetTypeLibFromMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="765cc-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>

<span data-ttu-id="765cc-103">`ITypeLib`지정 된 라이브러리 및 모듈 이름이 있는 형식 라이브러리를 나타내는 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="765cc-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="765cc-104">구문</span><span class="sxs-lookup"><span data-stu-id="765cc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="765cc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="765cc-105">Parameters</span></span>  

 `strModule`  
 <span data-ttu-id="765cc-106">진행 형식 라이브러리의 모듈 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="765cc-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="765cc-107">진행 형식 라이브러리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="765cc-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="765cc-108">제한이 형식 라이브러리를 나타내는 인스턴스의 주소를 받는 위치에 대 한 포인터 `ITypeLib` 입니다.</span><span class="sxs-lookup"><span data-stu-id="765cc-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="765cc-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="765cc-109">Requirements</span></span>  

 <span data-ttu-id="765cc-110">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="765cc-110">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="765cc-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="765cc-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="765cc-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="765cc-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="765cc-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="765cc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="765cc-114">참조</span><span class="sxs-lookup"><span data-stu-id="765cc-114">See also</span></span>

- [<span data-ttu-id="765cc-115">IMetaDataConverter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="765cc-115">IMetaDataConverter Interface</span></span>](imetadataconverter-interface.md)

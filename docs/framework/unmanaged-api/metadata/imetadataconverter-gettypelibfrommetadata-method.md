---
description: '자세히 알아보기: IMetaDataConverter:: GetTypeLibFromMetaData 메서드'
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
ms.openlocfilehash: 5eecc87f938740366b7938d6ec3d1460ebcfb7eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789270"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="d74ed-103">IMetaDataConverter::GetTypeLibFromMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="d74ed-103">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>

<span data-ttu-id="d74ed-104">`ITypeLib`지정 된 라이브러리 및 모듈 이름이 있는 형식 라이브러리를 나타내는 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d74ed-104">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d74ed-105">구문</span><span class="sxs-lookup"><span data-stu-id="d74ed-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d74ed-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d74ed-106">Parameters</span></span>  

 `strModule`  
 <span data-ttu-id="d74ed-107">진행 형식 라이브러리의 모듈 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d74ed-107">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="d74ed-108">진행 형식 라이브러리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d74ed-108">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="d74ed-109">제한이 형식 라이브러리를 나타내는 인스턴스의 주소를 받는 위치에 대 한 포인터 `ITypeLib` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d74ed-109">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d74ed-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d74ed-110">Requirements</span></span>  

 <span data-ttu-id="d74ed-111">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d74ed-111">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d74ed-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="d74ed-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d74ed-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d74ed-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d74ed-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d74ed-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d74ed-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d74ed-115">See also</span></span>

- [<span data-ttu-id="d74ed-116">IMetaDataConverter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d74ed-116">IMetaDataConverter Interface</span></span>](imetadataconverter-interface.md)

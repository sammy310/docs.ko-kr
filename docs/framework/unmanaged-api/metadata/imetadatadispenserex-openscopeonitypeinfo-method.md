---
description: '자세히 알아보기: IMetaDataDispenserEx:: OpenScopeOnITypeInfo 메서드'
title: IMetaDataDispenserEx::OpenScopeOnITypeInfo 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.OpenScopeOnITypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::OpenScopeOnITypeInfo
helpviewer_keywords:
- OpenScopeOnITypeInfo method [.NET Framework metadata]
- IMetaDataDispenserEx::OpenScopeOnITypeInfo method [.NET Framework metadata]
ms.assetid: 3480bbdb-c442-44a0-b7c6-333354503c52
topic_type:
- apiref
ms.openlocfilehash: bc36bac9e7c63f56f442f1e25fd7a6a93f75924b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753525"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="9c307-103">IMetaDataDispenserEx::OpenScopeOnITypeInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="9c307-103">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>

<span data-ttu-id="9c307-104">이 메서드가 구현되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="9c307-104">This method is not implemented.</span></span> <span data-ttu-id="9c307-105">이 메서드를 호출 하면 E_NOTIMPL 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c307-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c307-106">구문</span><span class="sxs-lookup"><span data-stu-id="9c307-106">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c307-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9c307-107">Parameters</span></span>  

 `pITI`  
 <span data-ttu-id="9c307-108">진행 범위를 열 수 있는 형식 정보를 제공 하는 [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9c307-108">[in] Pointer to an [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="9c307-109">진행 열기 모드 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="9c307-109">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="9c307-110">진행 원하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9c307-110">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="9c307-111">제한이 반환 된 인터페이스에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9c307-111">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c307-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9c307-112">Requirements</span></span>  

 <span data-ttu-id="9c307-113">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c307-113">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c307-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="9c307-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9c307-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c307-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9c307-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c307-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c307-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c307-117">See also</span></span>

- [<span data-ttu-id="9c307-118">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c307-118">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="9c307-119">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c307-119">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)

---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: deecd9ed4161bbd72e97a6320188961ae76d1e7c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044267"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="f60ec-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="f60ec-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="f60ec-103">이 메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f60ec-103">This method is not implemented.</span></span> <span data-ttu-id="f60ec-104">를 호출 하는 경우 E_NOTIMPL을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60ec-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f60ec-105">구문</span><span class="sxs-lookup"><span data-stu-id="f60ec-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f60ec-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f60ec-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="f60ec-107">[in] 에 대 한 포인터를 [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) 를 범위를 열 형식 정보를 제공 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f60ec-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="f60ec-108">[in] 오픈 모드 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="f60ec-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="f60ec-109">[in] 원하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f60ec-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="f60ec-110">[out] 반환 되는 인터페이스에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f60ec-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f60ec-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f60ec-111">Requirements</span></span>  
 <span data-ttu-id="f60ec-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f60ec-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f60ec-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f60ec-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f60ec-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="f60ec-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f60ec-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f60ec-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f60ec-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="f60ec-116">See also</span></span>

- [<span data-ttu-id="f60ec-117">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f60ec-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="f60ec-118">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f60ec-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)

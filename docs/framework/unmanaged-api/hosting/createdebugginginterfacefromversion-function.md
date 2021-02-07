---
description: '자세히 알아보기: CreateDebuggingInterfaceFromVersion 함수'
title: CreateDebuggingInterfaceFromVersion 함수
ms.date: 03/30/2017
api_name:
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
ms.openlocfilehash: 163ada49f028071b48c93ee3c565152a773782ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760632"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="27480-103">CreateDebuggingInterfaceFromVersion 함수</span><span class="sxs-lookup"><span data-stu-id="27480-103">CreateDebuggingInterfaceFromVersion Function</span></span>

<span data-ttu-id="27480-104">지정 된 버전 정보를 기반으로 [ICorDebug](../debugging/icordebug-interface.md) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27480-104">Creates an [ICorDebug](../debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="27480-105">이 함수는 .NET Framework 4에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27480-105">This function is obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="27480-106">대신 CLR (공용 언어 런타임) 2.0에 대 한 인터페이스를 가져오려면 [ICLRRuntimeInfo:: GetInterface](iclrruntimeinfo-getinterface-method.md) 메서드를 사용 하 고 클래스 식별자 CLSID_CLRDebuggingLegacy 및 인터페이스 식별자 IID_ICorDebug를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27480-106">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="27480-107">CLR 4 이상에 대 한 인터페이스를 가져오려면 [Clrcreateinstance](clrcreateinstance-function.md) 함수를 호출 하 고 클래스 식별자 CLSID_CLRDebugging 및 인터페이스 식별자 IID_ICLRDebugging를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27480-107">To get an interface for CLR 4 or later, call the [CLRCreateInstance](clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27480-108">구문</span><span class="sxs-lookup"><span data-stu-id="27480-108">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27480-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="27480-109">Parameters</span></span>  

 `iDebuggerVersion`  
 <span data-ttu-id="27480-110">진행 디버거에 필요한의 버전입니다 `ICorDebug` .</span><span class="sxs-lookup"><span data-stu-id="27480-110">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="27480-111">올바른 값은 [Cordebuginterfaceversion](../debugging/cordebuginterfaceversion-enumeration.md) 열거형을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="27480-111">See the [CorDebugInterfaceVersion](../debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="27480-112">진행 디버그할 응용 프로그램 또는 프로세스와 연결 된 공용 언어 런타임 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="27480-112">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="27480-113">이 값을 검색 하는 방법에 대 한 자세한 내용은 [Getversionfromprocess](getversionfromprocess-function.md) 또는 [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="27480-113">See the [GetVersionFromProcess](getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="27480-114">제한이 개체에 대 한 포인터를 수신 하는 위치입니다 `ICorDebug` .</span><span class="sxs-lookup"><span data-stu-id="27480-114">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27480-115">Return Value</span><span class="sxs-lookup"><span data-stu-id="27480-115">Return Value</span></span>  

 <span data-ttu-id="27480-116">이 메서드는 다음 값 외에도 Winerror.h 파일에 정의 된 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="27480-116">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="27480-117">반환 코드</span><span class="sxs-lookup"><span data-stu-id="27480-117">Return code</span></span>|<span data-ttu-id="27480-118">설명</span><span class="sxs-lookup"><span data-stu-id="27480-118">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="27480-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="27480-119">S_OK</span></span>|<span data-ttu-id="27480-120">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="27480-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="27480-121">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="27480-121">E_INVALIDARG</span></span>|<span data-ttu-id="27480-122">`szDebuggeeVersion` 또는 `ppCordb` 이 null 이거나 버전 문자열이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="27480-122">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27480-123">설명</span><span class="sxs-lookup"><span data-stu-id="27480-123">Remarks</span></span>  

 <span data-ttu-id="27480-124">`szDebuggeeVersion`매개 변수는 해당 하는 버전의 MSCorDbi.dll에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="27480-124">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27480-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27480-125">Requirements</span></span>  

 <span data-ttu-id="27480-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27480-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27480-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="27480-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27480-128">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="27480-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27480-129">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27480-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27480-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27480-130">See also</span></span>

- [<span data-ttu-id="27480-131">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="27480-131">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)

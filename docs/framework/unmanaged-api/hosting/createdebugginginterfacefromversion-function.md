---
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
ms.openlocfilehash: adc8ea16f0ab2bf383f8a63c49ba7d61c6bac113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176450"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="297a6-102">CreateDebuggingInterfaceFromVersion 함수</span><span class="sxs-lookup"><span data-stu-id="297a6-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="297a6-103">지정된 버전 정보를 기반으로 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="297a6-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="297a6-104">이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="297a6-104">This function is obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="297a6-105">대신 공통 언어 런타임(CLR) 2.0에 대한 인터페이스를 얻으려면 [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) 메서드를 사용하고 클래스 식별자 CLSID_CLRDebuggingLegacy 및 인터페이스 식별자를 IID_ICorDebug 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="297a6-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="297a6-106">CLR 4 이상에 대한 인터페이스를 얻으려면 [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) 함수를 호출하고 클래스 식별자 CLSID_CLRDebugging 및 인터페이스 식별자를 IID_ICLRDebugging 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="297a6-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="297a6-107">구문</span><span class="sxs-lookup"><span data-stu-id="297a6-107">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="297a6-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="297a6-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="297a6-109">【인】 `ICorDebug` 디버거에서 이 버전이 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="297a6-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="297a6-110">유효한 값은 [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) 열거를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="297a6-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="297a6-111">【인】 디버깅할 응용 프로그램 또는 프로세스와 연결된 공통 언어 런타임 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="297a6-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="297a6-112">이 값을 검색하는 방법에 대한 자세한 내용은 [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) 또는 [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) 메서드를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="297a6-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="297a6-113">【아웃】 개체에 대한 포인터를 `ICorDebug` 받는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="297a6-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="297a6-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="297a6-114">Return Value</span></span>  
 <span data-ttu-id="297a6-115">이 메서드는 다음 값 외에 WinError.h 파일에 정의된 표준 COM 오류 코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="297a6-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="297a6-116">반환 코드</span><span class="sxs-lookup"><span data-stu-id="297a6-116">Return code</span></span>|<span data-ttu-id="297a6-117">Description</span><span class="sxs-lookup"><span data-stu-id="297a6-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="297a6-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="297a6-118">S_OK</span></span>|<span data-ttu-id="297a6-119">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="297a6-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="297a6-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="297a6-120">E_INVALIDARG</span></span>|<span data-ttu-id="297a6-121">`szDebuggeeVersion`또는 `ppCordb` null이거나 버전 문자열이 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="297a6-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="297a6-122">설명</span><span class="sxs-lookup"><span data-stu-id="297a6-122">Remarks</span></span>  
 <span data-ttu-id="297a6-123">매개 `szDebuggeeVersion` 변수는 MSCorDbi.dll의 해당 버전에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="297a6-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="297a6-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="297a6-124">Requirements</span></span>  
 <span data-ttu-id="297a6-125">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="297a6-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="297a6-126">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="297a6-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="297a6-127">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="297a6-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="297a6-128">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="297a6-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="297a6-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="297a6-129">See also</span></span>

- [<span data-ttu-id="297a6-130">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="297a6-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

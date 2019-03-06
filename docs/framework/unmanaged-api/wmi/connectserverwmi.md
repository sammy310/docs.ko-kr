---
title: ConnectServerWmi 함수 (관리 되지 않는 API 참조)
description: ConnectServerWmi 함수 DCOM을 사용 하 여 WMI 네임 스페이스에 대 한 연결을 만듭니다.
ms.date: 11/06/2017
api_name:
- ConnectServerWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ConnectServerWmi
helpviewer_keywords:
- ConnectServerWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 548c6007d4ed685c521676de87c5a98f56a222a4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376990"
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="19ca5-103">ConnectServerWmi 함수</span><span class="sxs-lookup"><span data-stu-id="19ca5-103">ConnectServerWmi function</span></span>
<span data-ttu-id="19ca5-104">DCOM 통해 지정된 컴퓨터의 WMI 네임스페이스에 대한 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="19ca5-105">구문</span><span class="sxs-lookup"><span data-stu-id="19ca5-105">Syntax</span></span>

```
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel, 
   [in] DWORD              authLevel
);
```
## <a name="parameters"></a><span data-ttu-id="19ca5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="19ca5-106">Parameters</span></span>

`strNetworkResource`\
<span data-ttu-id="19ca5-107">[in] 유효한 포인터 `BSTR` 올바른 WMI 네임 스페이스의 개체 경로 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-107">[in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="19ca5-108">참조 된 [주의](#remarks) 자세한 내용은 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-108">See the [Remarks](#remarks) section for more information.</span></span>

`strUser`\
<span data-ttu-id="19ca5-109">[in] 유효한 포인터 `BSTR` 사용자 이름을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-109">[in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="19ca5-110">`null` 값 현재 보안 컨텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="19ca5-111">사용자가 현재 다른 도메인에서 `strUser` 백슬래시로 구분 된 사용자 이름과 도메인을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="19ca5-112">`strUser` 와 같은 사용자 계정 이름 (UPN) 형식에 있을 수도 있습니다 `userName@domainName`합니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-112">`strUser` can also be in user principal name (UPN) format, such as `userName@domainName`.</span></span> <span data-ttu-id="19ca5-113">참조 된 [주의](#remarks) 자세한 내용은 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-113">See the [Remarks](#remarks) section for more information.</span></span>

`strPassword`\
<span data-ttu-id="19ca5-114">[in] 유효한 포인터 `BSTR` 암호가 포함 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-114">[in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="19ca5-115">`null` 현재 보안 컨텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="19ca5-116">빈 문자열 ("") 유효한 빈 암호를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-116">An empty string ("") indicates a valid zero-length password.</span></span>

`strLocale`\
<span data-ttu-id="19ca5-117">[in] 유효한 포인터 `BSTR` 정보 검색에 대 한 올바른 로캘을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-117">[in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="19ca5-118">Microsoft 로캘 식별자에 대 한 문자열의 형식은 "MS\_*xxx*", 여기서 *xxx* 로캘 식별자 (LCID)를 나타내는 16 진수 형식 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="19ca5-119">잘못 된 로캘을 지정 되 면 메서드가 반환 `WBEM_E_INVALID_PARAMETER` 제외 하 고 Windows 7, 서버의 기본 로캘을 대신 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="19ca5-120">경우 ' null1에 현재 로캘을 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-120">If \`null1, the current locale is used.</span></span> 
 
`lSecurityFlags`\
<span data-ttu-id="19ca5-121">[in] 전달할 플래그를 `ConnectServerWmi` 메서드.</span><span class="sxs-lookup"><span data-stu-id="19ca5-121">[in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="19ca5-122">이 매개 변수에 대 한 영 (0) 값에 대 한 호출에서 결과 `ConnectServerWmi` 서버 연결 후에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="19ca5-123">이 응답 하지 무기한으로 손상 된 경우는 응용 프로그램에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="19ca5-124">다른 유효한 값은:</span><span class="sxs-lookup"><span data-stu-id="19ca5-124">The other valid values are:</span></span>

| <span data-ttu-id="19ca5-125">상수</span><span class="sxs-lookup"><span data-stu-id="19ca5-125">Constant</span></span>  | <span data-ttu-id="19ca5-126">값</span><span class="sxs-lookup"><span data-stu-id="19ca5-126">Value</span></span>  | <span data-ttu-id="19ca5-127">설명</span><span class="sxs-lookup"><span data-stu-id="19ca5-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="19ca5-128">0x40</span><span class="sxs-lookup"><span data-stu-id="19ca5-128">0x40</span></span> | <span data-ttu-id="19ca5-129">내부용으로 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-129">Reserved for internal use.</span></span> <span data-ttu-id="19ca5-130">사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="19ca5-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="19ca5-131">0x80</span><span class="sxs-lookup"><span data-stu-id="19ca5-131">0x80</span></span> | <span data-ttu-id="19ca5-132">`ConnectServerWmi` 2 분 이내에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

`strAuthority`\
<span data-ttu-id="19ca5-133">[in] 사용자의 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-133">[in] The domain name of the user.</span></span> <span data-ttu-id="19ca5-134">다음 값을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-134">It can have the following values:</span></span>

| <span data-ttu-id="19ca5-135">값</span><span class="sxs-lookup"><span data-stu-id="19ca5-135">Value</span></span> | <span data-ttu-id="19ca5-136">설명</span><span class="sxs-lookup"><span data-stu-id="19ca5-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="19ca5-137">비어 있음</span><span class="sxs-lookup"><span data-stu-id="19ca5-137">blank</span></span> | <span data-ttu-id="19ca5-138">NTLM 인증을 사용 하 고 현재 사용자의 NTLM 도메인이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="19ca5-139">경우 `strUser` 도메인을 지정 합니다 (권장 되는 위치), 여기 지정 되지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="19ca5-140">함수 반환 `WBEM_E_INVALID_PARAMETER` 매개 변수가 모두에서 도메인을 지정 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="19ca5-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="19ca5-141">Kerberos:*계정 이름*</span><span class="sxs-lookup"><span data-stu-id="19ca5-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="19ca5-142">Kerberos 인증을 사용 하 고이 매개 변수는 Kerberos 사용자 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="19ca5-143">NTLMDOMAIN:*도메인 이름*</span><span class="sxs-lookup"><span data-stu-id="19ca5-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="19ca5-144">NT LAN Manager 인증을 사용 하 고이 매개 변수는 NTLM 도메인 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`\
<span data-ttu-id="19ca5-145">[in] 이 매개 변수는 일반적으로 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-145">[in] Typically, this parameter is `null`.</span></span> <span data-ttu-id="19ca5-146">그렇지 않을 경우에 대 한 포인터를 [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) 개체가 하나 이상의 동적 클래스 공급자가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-146">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) object required by one or more dynamic class providers.</span></span> 

`ppNamespace`\
<span data-ttu-id="19ca5-147">[out] 함수가 반환할 때 수신에 대 한 포인터를 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) 개체가 지정된 된 네임 스페이스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-147">[out] When the function returns, receives a pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object bound to the specified namespace.</span></span> <span data-ttu-id="19ca5-148">가리키도록 설정 됩니다 `null` 오류가 발생 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="19ca5-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`\
<span data-ttu-id="19ca5-149">[in] 가장 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-149">[in] The impersonation level.</span></span>

`authLevel`\
<span data-ttu-id="19ca5-150">[in] 권한 부여 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="19ca5-151">반환 값</span><span class="sxs-lookup"><span data-stu-id="19ca5-151">Return value</span></span>

<span data-ttu-id="19ca5-152">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="19ca5-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="19ca5-153">상수</span><span class="sxs-lookup"><span data-stu-id="19ca5-153">Constant</span></span>  |<span data-ttu-id="19ca5-154">값</span><span class="sxs-lookup"><span data-stu-id="19ca5-154">Value</span></span>  |<span data-ttu-id="19ca5-155">설명</span><span class="sxs-lookup"><span data-stu-id="19ca5-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="19ca5-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="19ca5-156">0x80041001</span></span> | <span data-ttu-id="19ca5-157">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="19ca5-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="19ca5-158">0x80041008</span></span> | <span data-ttu-id="19ca5-159">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="19ca5-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="19ca5-160">0x80041006</span></span> | <span data-ttu-id="19ca5-161">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="19ca5-162">0</span><span class="sxs-lookup"><span data-stu-id="19ca5-162">0</span></span> | <span data-ttu-id="19ca5-163">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="19ca5-164">설명</span><span class="sxs-lookup"><span data-stu-id="19ca5-164">Remarks</span></span>

<span data-ttu-id="19ca5-165">이 함수에 대 한 호출을 래핑하는 [IWbemLocator::ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) 메서드.</span><span class="sxs-lookup"><span data-stu-id="19ca5-165">This function wraps a call to the [IWbemLocator::ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) method.</span></span>

<span data-ttu-id="19ca5-166">기본 네임 스페이스에 대 한 로컬 액세스에 대 한 `strNetworkResource` 단순 개체 경로일 수 있습니다. "root\default" 또는 "\\.\root\default"입니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="19ca5-167">원격 컴퓨터에서 기본 네임 스페이스에 대 한 액세스에 대 한 COM 또는 Microsoft 호환 네트워킹을 사용 하 여 컴퓨터 이름을 포함 합니다. "\\myserver\root\default"입니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="19ca5-168">또한 컴퓨터 이름을 DNS 이름 또는 IP 주소를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="19ca5-169">`ConnectServerWmi` 함수 IPv6을 실행 하는 컴퓨터에 연결할 수 IPv6 주소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="19ca5-170">`strUser` 빈 문자열일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="19ca5-171">도메인을 지정 하는 경우 `strAuthority`, 고 해야도에 포함 되지 `strUser`, 함수 반환 또는 `WBEM_E_INVALID_PARAMETER`합니다.</span><span class="sxs-lookup"><span data-stu-id="19ca5-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>


## <a name="requirements"></a><span data-ttu-id="19ca5-172">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19ca5-172">Requirements</span></span>

 <span data-ttu-id="19ca5-173">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="19ca5-173">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="19ca5-174">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="19ca5-174">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="19ca5-175">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="19ca5-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="19ca5-176">참고자료</span><span class="sxs-lookup"><span data-stu-id="19ca5-176">See also</span></span>

- [<span data-ttu-id="19ca5-177">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="19ca5-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
---
title: Certmgr.exe(인증서 관리자 도구)
description: 인증서 관리자 도구인 Certmgr.exe를 살펴봅니다. 이 도구는 인증서, CTL(인증서 신뢰 목록) 및 CRL(인증서 해지 목록)을 관리합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates, managing
- CRLs
- certificate trust lists
- Certmgr.exe
- Certificate Manager tool
- CTLs
- certificate revocation lists
ms.assetid: 7e953b43-1374-4bbc-814f-53ca1b6b52bb
ms.openlocfilehash: 30a35ded6fc86af6dc6dd4bf19cdf60f66570e0c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247254"
---
# <a name="certmgrexe-certificate-manager-tool"></a><span data-ttu-id="d60aa-104">Certmgr.exe(인증서 관리자 도구)</span><span class="sxs-lookup"><span data-stu-id="d60aa-104">Certmgr.exe (Certificate Manager Tool)</span></span>

<span data-ttu-id="d60aa-105">인증서 관리자 도구(Certmgr.exe)를 사용하면 인증서, CTL(인증서 신뢰 목록) 및 CRL(인증서 해지 목록)을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-105">The Certificate Manager tool (Certmgr.exe) manages certificates, certificate trust lists (CTLs), and certificate revocation lists (CRLs).</span></span>  
  
 <span data-ttu-id="d60aa-106">인증서 관리자는 Visual Studio와 함께 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-106">The Certificate Manager is automatically installed with Visual Studio.</span></span> <span data-ttu-id="d60aa-107">도구를 시작하려면 [명령 프롬프트](developer-command-prompt-for-vs.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-107">To start the tool, use the [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d60aa-108">인증서 관리자 도구(Certmgr.exe)는 명령줄 유틸리티인 반면, 인증서(Certmgr.msc)는 MMC(Microsoft Management Console) 스냅인입니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-108">The Certificate Manager tool (Certmgr.exe) is a command-line utility, whereas Certificates (Certmgr.msc) is a Microsoft Management Console (MMC) snap-in.</span></span> <span data-ttu-id="d60aa-109">Certmgr.msc는 대개 Windows 시스템 디렉터리에서 발견되기 때문에 명령줄에 `certmgr`을 입력하면 Visual Studio용 개발자 명령 프롬프트를 연 경우에도 인증서 MMC 스냅인을 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-109">Because Certmgr.msc is usually found in the Windows System directory, entering `certmgr` at the command line may load the Certificates MMC snap-in even if you have opened the Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="d60aa-110">이는 PATH 환경 변수에서 스냅인 경로가 인증서 관리자 도구로의 경로 앞에 오기 때문에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-110">This occurs because the path to the snap-in precedes the path to the Certificate Manager tool in the PATH environment variable.</span></span> <span data-ttu-id="d60aa-111">이 문제가 발생하는 경우 실행 파일에 대한 경로를 지정하여 Certmgr.exe 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-111">If you encounter this problem, you can execute Certmgr.exe commands by specifying the path to the executable.</span></span>  
  
 <span data-ttu-id="d60aa-112">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-112">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="d60aa-113">이 도구를 실행하려면 Visual Studio용 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-113">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="d60aa-114">자세한 내용은 [명령 프롬프트](developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d60aa-114">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="d60aa-115">X.509 인증서에 대한 개요는 [인증서 작업](../wcf/feature-details/working-with-certificates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d60aa-115">For an overview of X.509 certificates, see [Working with Certificates](../wcf/feature-details/working-with-certificates.md).</span></span>  
  
 <span data-ttu-id="d60aa-116">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-116">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d60aa-117">구문</span><span class="sxs-lookup"><span data-stu-id="d60aa-117">Syntax</span></span>  
  
```console  
      certmgr [/add | /del | /put] [options]  
[/s[/r registryLocation]] [sourceStorename]  
[/s[/r registryLocation]] [destinationStorename]  
```  
  
## <a name="parameters"></a><span data-ttu-id="d60aa-118">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d60aa-118">Parameters</span></span>  
  
|<span data-ttu-id="d60aa-119">인수</span><span class="sxs-lookup"><span data-stu-id="d60aa-119">Argument</span></span>|<span data-ttu-id="d60aa-120">설명</span><span class="sxs-lookup"><span data-stu-id="d60aa-120">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="d60aa-121">*sourceStorename*</span><span class="sxs-lookup"><span data-stu-id="d60aa-121">*sourceStorename*</span></span>|<span data-ttu-id="d60aa-122">추가, 삭제, 저장 또는 표시할 CRL 또는 CTL, 기존 인증서를 포함하는 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-122">The certificate store that contains the existing certificates, CTLs, or CRLs to add, delete, save, or display.</span></span> <span data-ttu-id="d60aa-123">이는 저장소 파일 또는 시스템 저장소가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-123">This can be a store file or a systems store.</span></span>|  
|<span data-ttu-id="d60aa-124">*destinationStorename*</span><span class="sxs-lookup"><span data-stu-id="d60aa-124">*destinationStorename*</span></span>|<span data-ttu-id="d60aa-125">출력 인증서 저장소 또는 파일을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-125">The output certificate store or file.</span></span>|  
  
|<span data-ttu-id="d60aa-126">옵션</span><span class="sxs-lookup"><span data-stu-id="d60aa-126">Option</span></span>|<span data-ttu-id="d60aa-127">설명</span><span class="sxs-lookup"><span data-stu-id="d60aa-127">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d60aa-128">**/add**</span><span class="sxs-lookup"><span data-stu-id="d60aa-128">**/add**</span></span>|<span data-ttu-id="d60aa-129">인증서, CTL 및 CRL을 인증서 저장소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-129">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>|  
|<span data-ttu-id="d60aa-130">**/all**</span><span class="sxs-lookup"><span data-stu-id="d60aa-130">**/all**</span></span>|<span data-ttu-id="d60aa-131">**/add** 옵션과 함께 사용하면 모든 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-131">Adds all entries when used with **/add**.</span></span> <span data-ttu-id="d60aa-132">**/del** 옵션과 함께 사용하면 모든 항목을 삭제합니다. **/add** 또는 **/del** 옵션 없이 사용하면 모든 항목을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-132">Deletes all entries when used with **/del**. Displays all entries when used without the **/add** or **/del** options.</span></span> <span data-ttu-id="d60aa-133">**/all** 옵션은 **/put** 과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-133">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="d60aa-134">**/c**</span><span class="sxs-lookup"><span data-stu-id="d60aa-134">**/c**</span></span>|<span data-ttu-id="d60aa-135">**/add** 옵션과 함께 사용하면 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-135">Adds certificates when used with **/add**.</span></span> <span data-ttu-id="d60aa-136">**/del** 옵션과 함께 사용하면 인증서를 삭제합니다. **/put** 옵션과 함께 사용하면 인증서를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-136">Deletes certificates when used with **/del**. Saves certificates when used with **/put**.</span></span> <span data-ttu-id="d60aa-137">**/add**, **/del** 또는 **/put** 옵션 없이 사용하면 인증서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-137">Displays certificates when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="d60aa-138">**/CRL**</span><span class="sxs-lookup"><span data-stu-id="d60aa-138">**/CRL**</span></span>|<span data-ttu-id="d60aa-139">**/add** 와 함께 사용하면 CRL을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-139">Adds CRLs when used with **/add**.</span></span> <span data-ttu-id="d60aa-140">**/del** 과 함께 사용하면 CRL을 삭제합니다. **/put** 과 함께 사용하면 CRL을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-140">Deletes CRLs when used with **/del**. Saves CRLs when used with **/put**.</span></span> <span data-ttu-id="d60aa-141">**/add**, **/del** 또는 **/put** 옵션 없이 사용하면 CRL을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-141">Displays CRLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="d60aa-142">**/CTL**</span><span class="sxs-lookup"><span data-stu-id="d60aa-142">**/CTL**</span></span>|<span data-ttu-id="d60aa-143">**/add** 와 함께 사용하면 CTL을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-143">Adds CTLs when used with **/add**.</span></span> <span data-ttu-id="d60aa-144">**/del** 과 함께 사용하면 CTL을 삭제합니다. **/put** 과 함께 사용하면 CTL을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-144">Deletes CTLs when used with **/del**. Saves CTLs when used with **/put**.</span></span> <span data-ttu-id="d60aa-145">**/add**, **/del** 또는 **/put** 옵션 없이 사용하면 CTL을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-145">Displays CTLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="d60aa-146">**/del**</span><span class="sxs-lookup"><span data-stu-id="d60aa-146">**/del**</span></span>|<span data-ttu-id="d60aa-147">인증서, CTL 및 CRL을 인증서 저장소에서 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-147">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>|  
|<span data-ttu-id="d60aa-148">**/e** *encodingType*</span><span class="sxs-lookup"><span data-stu-id="d60aa-148">**/e** *encodingType*</span></span>|<span data-ttu-id="d60aa-149">인증서 인코딩 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-149">Specifies the certificate encoding type.</span></span> <span data-ttu-id="d60aa-150">기본값은 `X509_ASN_ENCODING`입니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-150">The default is `X509_ASN_ENCODING`.</span></span>|  
|<span data-ttu-id="d60aa-151">**/f** *dwFlags*</span><span class="sxs-lookup"><span data-stu-id="d60aa-151">**/f** *dwFlags*</span></span>|<span data-ttu-id="d60aa-152">저장소 열기 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-152">Specifies the store open flag.</span></span> <span data-ttu-id="d60aa-153">저장소 열기 플래그는 **CertOpenStore** 에 전달되는 *dwFlags* 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-153">This is the *dwFlags* parameter passed to **CertOpenStore**.</span></span> <span data-ttu-id="d60aa-154">기본값은 CERT_SYSTEM_STORE_CURRENT_USER이고,</span><span class="sxs-lookup"><span data-stu-id="d60aa-154">The default value is CERT_SYSTEM_STORE_CURRENT_USER.</span></span> <span data-ttu-id="d60aa-155">이 옵션은 **/y** 옵션이 사용된 경우에만 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-155">This option is considered only if the **/y** option is used.</span></span>|  
|<span data-ttu-id="d60aa-156">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="d60aa-156">**/h**[**elp**]</span></span>|<span data-ttu-id="d60aa-157">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-157">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="d60aa-158">**/n** *nam*</span><span class="sxs-lookup"><span data-stu-id="d60aa-158">**/n** *nam*</span></span>|<span data-ttu-id="d60aa-159">추가, 삭제 또는 저장할 인증서의 일반 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-159">Specifies the common name of the certificate to add, delete, or save.</span></span> <span data-ttu-id="d60aa-160">이 옵션은 인증서에 대해서만 사용할 수 있으며, CTL 또는 CRL에 대해서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-160">This option can only be used with certificates; it cannot be used with CTLs or CRLs.</span></span>|  
|<span data-ttu-id="d60aa-161">**/put**</span><span class="sxs-lookup"><span data-stu-id="d60aa-161">**/put**</span></span>|<span data-ttu-id="d60aa-162">인증서 저장소의 X.509 인증서, CTL 또는 CRL을 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-162">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span> <span data-ttu-id="d60aa-163">이 파일은 X.509 형식으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-163">The file is saved in X.509 format.</span></span> <span data-ttu-id="d60aa-164">**/7** 옵션을 **/put** 옵션과 함께 사용하여 파일을 PKCS #7 형식으로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-164">You can use the **/7** option with the **/put** option to save the file in PKCS #7 format.</span></span> <span data-ttu-id="d60aa-165">**/put** 옵션 다음에는 **/c**, **/CTL** 또는 **/CRL** 중 하나를 사용해야 하며,</span><span class="sxs-lookup"><span data-stu-id="d60aa-165">The **/put** option must be followed by either **/c**, **/CTL**, or **/CRL**.</span></span> <span data-ttu-id="d60aa-166">**/all** 옵션은 **/put** 과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-166">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="d60aa-167">**/r** *location*</span><span class="sxs-lookup"><span data-stu-id="d60aa-167">**/r** *location*</span></span>|<span data-ttu-id="d60aa-168">시스템 저장소의 레지스트리 위치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-168">Identifies the registry location of the system store.</span></span> <span data-ttu-id="d60aa-169">이 옵션은 **/s** 옵션을 지정하는 경우에만 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-169">This option is considered only if you specify the **/s** option.</span></span> <span data-ttu-id="d60aa-170">*위치* 는 다음 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-170">*location* must be one of the following:</span></span><br /><br /> <span data-ttu-id="d60aa-171">-   `currentUser`는 인증서 저장소가 HKEY_CURRENT_USER 키 아래에 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-171">-   `currentUser` indicates that the certificate store is under the HKEY_CURRENT_USER key.</span></span> <span data-ttu-id="d60aa-172">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-172">This is the default.</span></span><br /><span data-ttu-id="d60aa-173">-   `localMachine`은 인증서 저장소가 HKEY_LOCAL_MACHINE 키 아래에 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-173">-   `localMachine` indicates that the certificate store is under the HKEY_LOCAL_MACHINE key.</span></span>|  
|<span data-ttu-id="d60aa-174">**/s**</span><span class="sxs-lookup"><span data-stu-id="d60aa-174">**/s**</span></span>|<span data-ttu-id="d60aa-175">인증서 저장소가 시스템 저장소임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-175">Indicates that the certificate store is a system store.</span></span> <span data-ttu-id="d60aa-176">이 옵션을 지정하지 않으면 저장소가 **StoreFile** 로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-176">If you do not specify this option, the store is considered to be a **StoreFile**.</span></span>|  
|<span data-ttu-id="d60aa-177">**/sha1** *sha1Hash*</span><span class="sxs-lookup"><span data-stu-id="d60aa-177">**/sha1** *sha1Hash*</span></span>|<span data-ttu-id="d60aa-178">추가, 삭제 또는 저장할 인증서, CTL 또는 CRL의 SHA1 해시를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-178">Specifies the SHA1 hash of the certificate, CTL, or CRL to add, delete, or save.</span></span>|  
|<span data-ttu-id="d60aa-179">**/v**</span><span class="sxs-lookup"><span data-stu-id="d60aa-179">**/v**</span></span>|<span data-ttu-id="d60aa-180">세부 정보 표시 모드를 지정합니다. 즉, 인증서, CTL 및 CRL에 대한 자세한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-180">Specifies verbose mode; displays detailed information about certificates, CTLs, and CRLs.</span></span> <span data-ttu-id="d60aa-181">이 옵션은 **/add**, **/del** 또는 **/put** 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-181">This option cannot be used with the **/add**, **/del**, or **/put** options.</span></span>|  
|<span data-ttu-id="d60aa-182">**/y** *provider*</span><span class="sxs-lookup"><span data-stu-id="d60aa-182">**/y** *provider*</span></span>|<span data-ttu-id="d60aa-183">저장소 공급자의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-183">Specifies the store provider name.</span></span>|  
|<span data-ttu-id="d60aa-184">**/7**</span><span class="sxs-lookup"><span data-stu-id="d60aa-184">**/7**</span></span>|<span data-ttu-id="d60aa-185">대상 저장소를 PKCS #7 개체로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-185">Saves the destination store as a PKCS #7 object.</span></span>|  
|<span data-ttu-id="d60aa-186">**/?**</span><span class="sxs-lookup"><span data-stu-id="d60aa-186">**/?**</span></span>|<span data-ttu-id="d60aa-187">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-187">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d60aa-188">설명</span><span class="sxs-lookup"><span data-stu-id="d60aa-188">Remarks</span></span>  

 <span data-ttu-id="d60aa-189">Certmgr.exe를 사용하여 다음과 같은 기본 기능을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-189">Certmgr.exe performs the following basic functions:</span></span>  
  
- <span data-ttu-id="d60aa-190">인증서, CTL 및 CRL을 콘솔에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-190">Displays certificates, CTLs, and CRLs to the console.</span></span>  
  
- <span data-ttu-id="d60aa-191">인증서, CTL 및 CRL을 인증서 저장소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-191">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>  
  
- <span data-ttu-id="d60aa-192">인증서, CTL 및 CRL을 인증서 저장소에서 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-192">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>  
  
- <span data-ttu-id="d60aa-193">인증서 저장소의 X.509 인증서, CTL 또는 CRL을 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-193">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span>  
  
 <span data-ttu-id="d60aa-194">Certmgr.exe를 사용하면 다음과 같은 두 가지 형식의 인증서 저장소를 사용하여 작업할 수 있습니다. **StoreFile** 및 시스템 저장소.</span><span class="sxs-lookup"><span data-stu-id="d60aa-194">Certmgr.exe works with two types of certificate stores: **StoreFile** and system store.</span></span> <span data-ttu-id="d60aa-195">그러나 Certmgr.exe로 저장소 형식을 식별한 다음 적합한 작업을 수행할 수 있으므로 인증서 저장소 형식을 지정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-195">It is not necessary to specify the type of certificate store; Certmgr.exe can identify the store type and perform the appropriate operations.</span></span>  
  
 <span data-ttu-id="d60aa-196">옵션을 지정하지 않고 Certmgr.exe를 실행하면 명령줄에서도 사용할 수 있는 인증서 관리 작업을 돕는 GUI인 certmgr.msc snap-in이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-196">Running Certmgr.exe without specifying any options launches the certmgr.msc snap-in, which has a GUI that helps with the certificate management tasks that are also available from the command line.</span></span> <span data-ttu-id="d60aa-197">이 GUI를 통해 디스크의 인증서, CTL 및 CRL을 인증서 저장소에 복사하는 가져오기 마법사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-197">The GUI provides an import wizard, which copies certificates, CTLs, and CRLs from your disk to a certificate store.</span></span>  
  
 <span data-ttu-id="d60aa-198">`sourceStorename` 및 `destinationStorename` 매개 변수에 대한 X509Certificate 저장소의 이름을 다음 코드를 컴파일 및 실행하여 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-198">You can find the names of X509Certificate stores for the `sourceStorename` and `destinationStorename` parameters by compiling and running the following code.</span></span>  
  
 [!code-csharp[Tools.CertMgr#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tools.certmgr/cs/storenames1.cs#1)]
 [!code-vb[Tools.CertMgr#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tools.certmgr/vb/storenames1.vb#1)]  
  
 <span data-ttu-id="d60aa-199">자세한 내용은 [인증서 작업](../wcf/feature-details/working-with-certificates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d60aa-199">For more information about certificates, see [Working with Certificates](../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d60aa-200">예</span><span class="sxs-lookup"><span data-stu-id="d60aa-200">Examples</span></span>  

 <span data-ttu-id="d60aa-201">다음 명령을 사용하여 `my`라는 기본 시스템 저장소를 자세한 정보와 함께 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-201">The following command displays a default system store called `my` with verbose output.</span></span>  
  
```console  
certmgr /v /s my  
```  
  
 <span data-ttu-id="d60aa-202">다음 명령을 사용하여 `myFile.ext`라는 파일에 있는 모든 인증서를 `newFile.ext`라는 새 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-202">The following command adds all the certificates in a file called `myFile.ext` to a new file called `newFile.ext`.</span></span>  
  
```console  
certmgr /add /all /c myFile.ext newFile.ext  
```  
  
 <span data-ttu-id="d60aa-203">다음 명령은 `testcert.cer`이라는 파일의 인증서를 `my` 시스템 저장소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-203">The following command adds the certificate in a file named `testcert.cer` to the `my` system store.</span></span>  
  
```console  
certmgr /add /c testcert.cer /s my  
```  
  
 <span data-ttu-id="d60aa-204">다음 명령은 `TrustedCert.cer`이라는 파일의 인증서를 루트 인증서 저장소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-204">The following command adds the certificate in a file named `TrustedCert.cer` to the root certificate store.</span></span>  
  
```console  
certmgr /c /add TrustedCert.cer /s root  
```  
  
 <span data-ttu-id="d60aa-205">다음 명령을 사용하여 `myCert`시스템 저장소에 있는 `my`라는 일반 이름의 인증서를 `newCert.cer`이라는 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-205">The following command saves a certificate with the common name `myCert` in the `my` system store to a file called `newCert.cer`.</span></span>  
  
```console  
certmgr /add /c /n myCert /s my newCert.cer  
```  
  
 <span data-ttu-id="d60aa-206">다음 명령을 사용하여 `my` 시스템 저장소에 있는 모든 CTL을 삭제하고 그 결과로 만들어지는 저장소를 `newStore.str`이라는 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-206">The following command deletes all CTLs in the `my` system store and saves the resulting store to a file called `newStore.str`.</span></span>  
  
```console  
certmgr /del /all /ctl /s my newStore.str  
```  
  
 <span data-ttu-id="d60aa-207">다음 명령을 사용하여 `my`시스템 저장소의 인증서를 `newFile` 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-207">The following command saves a certificate in the `my` system store in the file `newFile`.</span></span> <span data-ttu-id="d60aa-208">그러면 `my`에 넣을 `newFile`의 인증서 번호를 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60aa-208">You will be prompted to enter the certificate number from `my` to put in `newFile`.</span></span>  
  
```console  
certmgr /put /c /s my newFile  
```  
  
## <a name="see-also"></a><span data-ttu-id="d60aa-209">참조</span><span class="sxs-lookup"><span data-stu-id="d60aa-209">See also</span></span>

- [<span data-ttu-id="d60aa-210">도구</span><span class="sxs-lookup"><span data-stu-id="d60aa-210">Tools</span></span>](index.md)
- [<span data-ttu-id="d60aa-211">Makecert.exe(인증서 작성 도구)</span><span class="sxs-lookup"><span data-stu-id="d60aa-211">Makecert.exe (Certificate Creation Tool)</span></span>](/windows/desktop/SecCrypto/makecert)
- [<span data-ttu-id="d60aa-212">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="d60aa-212">Command Prompts</span></span>](developer-command-prompt-for-vs.md)

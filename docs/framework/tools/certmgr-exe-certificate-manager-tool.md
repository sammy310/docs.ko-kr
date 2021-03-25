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
ms.openlocfilehash: eba8253a52f9dc533848fc7cbb76566c726495a2
ms.sourcegitcommit: 1dbe25ff484a02025d5c34146e517c236f7161fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "104654195"
---
# <a name="certmgrexe-certificate-manager-tool"></a><span data-ttu-id="69ea6-104">Certmgr.exe(인증서 관리자 도구)</span><span class="sxs-lookup"><span data-stu-id="69ea6-104">Certmgr.exe (Certificate Manager Tool)</span></span>

<span data-ttu-id="69ea6-105">인증서 관리자 도구(Certmgr.exe)를 사용하면 인증서, CTL(인증서 신뢰 목록) 및 CRL(인증서 해지 목록)을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-105">The Certificate Manager tool (Certmgr.exe) manages certificates, certificate trust lists (CTLs), and certificate revocation lists (CRLs).</span></span>  
  
 <span data-ttu-id="69ea6-106">인증서 관리자는 Visual Studio와 함께 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-106">The Certificate Manager is automatically installed with Visual Studio.</span></span> <span data-ttu-id="69ea6-107">도구를 시작하려면 [Visual Studio 개발자 명령 프롬프트 또는 Visual Studio 개발자 PowerShell](/visualstudio/ide/reference/command-prompt-powershell)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-107">To start the tool, use [Visual Studio Developer Command Prompt or Visual Studio Developer PowerShell](/visualstudio/ide/reference/command-prompt-powershell).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69ea6-108">인증서 관리자 도구(Certmgr.exe)는 명령줄 유틸리티인 반면, 인증서(Certmgr.msc)는 MMC(Microsoft Management Console) 스냅인입니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-108">The Certificate Manager tool (Certmgr.exe) is a command-line utility, whereas Certificates (Certmgr.msc) is a Microsoft Management Console (MMC) snap-in.</span></span> <span data-ttu-id="69ea6-109">Certmgr.msc는 대개 Windows 시스템 디렉터리에서 발견되기 때문에 명령줄에 `certmgr`을 입력하면 Visual Studio용 개발자 명령 프롬프트를 연 경우에도 인증서 MMC 스냅인을 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-109">Because Certmgr.msc is usually found in the Windows System directory, entering `certmgr` at the command line may load the Certificates MMC snap-in even if you have opened the Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="69ea6-110">이는 PATH 환경 변수에서 스냅인 경로가 인증서 관리자 도구로의 경로 앞에 오기 때문에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-110">This occurs because the path to the snap-in precedes the path to the Certificate Manager tool in the PATH environment variable.</span></span> <span data-ttu-id="69ea6-111">이 문제가 발생하는 경우 실행 파일에 대한 경로를 지정하여 Certmgr.exe 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-111">If you encounter this problem, you can execute Certmgr.exe commands by specifying the path to the executable.</span></span>
  
 <span data-ttu-id="69ea6-112">X.509 인증서에 대한 개요는 [인증서 작업](../wcf/feature-details/working-with-certificates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69ea6-112">For an overview of X.509 certificates, see [Working with Certificates](../wcf/feature-details/working-with-certificates.md).</span></span>  
  
 <span data-ttu-id="69ea6-113">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-113">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69ea6-114">구문</span><span class="sxs-lookup"><span data-stu-id="69ea6-114">Syntax</span></span>  
  
```console  
      certmgr [/add | /del | /put] [options]  
[/s[/r registryLocation]] [sourceStorename]  
[/s[/r registryLocation]] [destinationStorename]  
```  
  
## <a name="parameters"></a><span data-ttu-id="69ea6-115">매개 변수</span><span class="sxs-lookup"><span data-stu-id="69ea6-115">Parameters</span></span>  
  
|<span data-ttu-id="69ea6-116">인수</span><span class="sxs-lookup"><span data-stu-id="69ea6-116">Argument</span></span>|<span data-ttu-id="69ea6-117">설명</span><span class="sxs-lookup"><span data-stu-id="69ea6-117">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="69ea6-118">*sourceStorename*</span><span class="sxs-lookup"><span data-stu-id="69ea6-118">*sourceStorename*</span></span>|<span data-ttu-id="69ea6-119">추가, 삭제, 저장 또는 표시할 CRL 또는 CTL, 기존 인증서를 포함하는 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-119">The certificate store that contains the existing certificates, CTLs, or CRLs to add, delete, save, or display.</span></span> <span data-ttu-id="69ea6-120">이는 저장소 파일 또는 시스템 저장소가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-120">This can be a store file or a systems store.</span></span>|  
|<span data-ttu-id="69ea6-121">*destinationStorename*</span><span class="sxs-lookup"><span data-stu-id="69ea6-121">*destinationStorename*</span></span>|<span data-ttu-id="69ea6-122">출력 인증서 저장소 또는 파일을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-122">The output certificate store or file.</span></span>|  
  
|<span data-ttu-id="69ea6-123">옵션</span><span class="sxs-lookup"><span data-stu-id="69ea6-123">Option</span></span>|<span data-ttu-id="69ea6-124">설명</span><span class="sxs-lookup"><span data-stu-id="69ea6-124">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="69ea6-125">**/add**</span><span class="sxs-lookup"><span data-stu-id="69ea6-125">**/add**</span></span>|<span data-ttu-id="69ea6-126">인증서, CTL 및 CRL을 인증서 저장소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-126">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>|  
|<span data-ttu-id="69ea6-127">**/all**</span><span class="sxs-lookup"><span data-stu-id="69ea6-127">**/all**</span></span>|<span data-ttu-id="69ea6-128">**/add** 옵션과 함께 사용하면 모든 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-128">Adds all entries when used with **/add**.</span></span> <span data-ttu-id="69ea6-129">**/del** 옵션과 함께 사용하면 모든 항목을 삭제합니다. **/add** 또는 **/del** 옵션 없이 사용하면 모든 항목을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-129">Deletes all entries when used with **/del**. Displays all entries when used without the **/add** or **/del** options.</span></span> <span data-ttu-id="69ea6-130">**/all** 옵션은 **/put** 과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-130">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="69ea6-131">**/c**</span><span class="sxs-lookup"><span data-stu-id="69ea6-131">**/c**</span></span>|<span data-ttu-id="69ea6-132">**/add** 옵션과 함께 사용하면 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-132">Adds certificates when used with **/add**.</span></span> <span data-ttu-id="69ea6-133">**/del** 옵션과 함께 사용하면 인증서를 삭제합니다. **/put** 옵션과 함께 사용하면 인증서를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-133">Deletes certificates when used with **/del**. Saves certificates when used with **/put**.</span></span> <span data-ttu-id="69ea6-134">**/add**, **/del** 또는 **/put** 옵션 없이 사용하면 인증서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-134">Displays certificates when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="69ea6-135">**/CRL**</span><span class="sxs-lookup"><span data-stu-id="69ea6-135">**/CRL**</span></span>|<span data-ttu-id="69ea6-136">**/add** 와 함께 사용하면 CRL을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-136">Adds CRLs when used with **/add**.</span></span> <span data-ttu-id="69ea6-137">**/del** 과 함께 사용하면 CRL을 삭제합니다. **/put** 과 함께 사용하면 CRL을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-137">Deletes CRLs when used with **/del**. Saves CRLs when used with **/put**.</span></span> <span data-ttu-id="69ea6-138">**/add**, **/del** 또는 **/put** 옵션 없이 사용하면 CRL을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-138">Displays CRLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="69ea6-139">**/CTL**</span><span class="sxs-lookup"><span data-stu-id="69ea6-139">**/CTL**</span></span>|<span data-ttu-id="69ea6-140">**/add** 와 함께 사용하면 CTL을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-140">Adds CTLs when used with **/add**.</span></span> <span data-ttu-id="69ea6-141">**/del** 과 함께 사용하면 CTL을 삭제합니다. **/put** 과 함께 사용하면 CTL을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-141">Deletes CTLs when used with **/del**. Saves CTLs when used with **/put**.</span></span> <span data-ttu-id="69ea6-142">**/add**, **/del** 또는 **/put** 옵션 없이 사용하면 CTL을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-142">Displays CTLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="69ea6-143">**/del**</span><span class="sxs-lookup"><span data-stu-id="69ea6-143">**/del**</span></span>|<span data-ttu-id="69ea6-144">인증서, CTL 및 CRL을 인증서 저장소에서 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-144">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>|  
|<span data-ttu-id="69ea6-145">**/e** *encodingType*</span><span class="sxs-lookup"><span data-stu-id="69ea6-145">**/e** *encodingType*</span></span>|<span data-ttu-id="69ea6-146">인증서 인코딩 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-146">Specifies the certificate encoding type.</span></span> <span data-ttu-id="69ea6-147">기본값은 `X509_ASN_ENCODING`입니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-147">The default is `X509_ASN_ENCODING`.</span></span>|  
|<span data-ttu-id="69ea6-148">**/f** *dwFlags*</span><span class="sxs-lookup"><span data-stu-id="69ea6-148">**/f** *dwFlags*</span></span>|<span data-ttu-id="69ea6-149">저장소 열기 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-149">Specifies the store open flag.</span></span> <span data-ttu-id="69ea6-150">저장소 열기 플래그는 **CertOpenStore** 에 전달되는 *dwFlags* 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-150">This is the *dwFlags* parameter passed to **CertOpenStore**.</span></span> <span data-ttu-id="69ea6-151">기본값은 CERT_SYSTEM_STORE_CURRENT_USER이고,</span><span class="sxs-lookup"><span data-stu-id="69ea6-151">The default value is CERT_SYSTEM_STORE_CURRENT_USER.</span></span> <span data-ttu-id="69ea6-152">이 옵션은 **/y** 옵션이 사용된 경우에만 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-152">This option is considered only if the **/y** option is used.</span></span>|  
|<span data-ttu-id="69ea6-153">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="69ea6-153">**/h**[**elp**]</span></span>|<span data-ttu-id="69ea6-154">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-154">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="69ea6-155">**/n** *nam*</span><span class="sxs-lookup"><span data-stu-id="69ea6-155">**/n** *nam*</span></span>|<span data-ttu-id="69ea6-156">추가, 삭제 또는 저장할 인증서의 일반 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-156">Specifies the common name of the certificate to add, delete, or save.</span></span> <span data-ttu-id="69ea6-157">이 옵션은 인증서에 대해서만 사용할 수 있으며, CTL 또는 CRL에 대해서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-157">This option can only be used with certificates; it cannot be used with CTLs or CRLs.</span></span>|  
|<span data-ttu-id="69ea6-158">**/put**</span><span class="sxs-lookup"><span data-stu-id="69ea6-158">**/put**</span></span>|<span data-ttu-id="69ea6-159">인증서 저장소의 X.509 인증서, CTL 또는 CRL을 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-159">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span> <span data-ttu-id="69ea6-160">이 파일은 X.509 형식으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-160">The file is saved in X.509 format.</span></span> <span data-ttu-id="69ea6-161">**/7** 옵션을 **/put** 옵션과 함께 사용하여 파일을 PKCS #7 형식으로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-161">You can use the **/7** option with the **/put** option to save the file in PKCS #7 format.</span></span> <span data-ttu-id="69ea6-162">**/put** 옵션 다음에는 **/c**, **/CTL** 또는 **/CRL** 중 하나를 사용해야 하며,</span><span class="sxs-lookup"><span data-stu-id="69ea6-162">The **/put** option must be followed by either **/c**, **/CTL**, or **/CRL**.</span></span> <span data-ttu-id="69ea6-163">**/all** 옵션은 **/put** 과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-163">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="69ea6-164">**/r** *location*</span><span class="sxs-lookup"><span data-stu-id="69ea6-164">**/r** *location*</span></span>|<span data-ttu-id="69ea6-165">시스템 저장소의 레지스트리 위치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-165">Identifies the registry location of the system store.</span></span> <span data-ttu-id="69ea6-166">이 옵션은 **/s** 옵션을 지정하는 경우에만 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-166">This option is considered only if you specify the **/s** option.</span></span> <span data-ttu-id="69ea6-167">*위치* 는 다음 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-167">*location* must be one of the following:</span></span><br /><br /> <span data-ttu-id="69ea6-168">-   `currentUser`는 인증서 저장소가 HKEY_CURRENT_USER 키 아래에 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-168">-   `currentUser` indicates that the certificate store is under the HKEY_CURRENT_USER key.</span></span> <span data-ttu-id="69ea6-169">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-169">This is the default.</span></span><br /><span data-ttu-id="69ea6-170">-   `localMachine`은 인증서 저장소가 HKEY_LOCAL_MACHINE 키 아래에 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-170">-   `localMachine` indicates that the certificate store is under the HKEY_LOCAL_MACHINE key.</span></span>|  
|<span data-ttu-id="69ea6-171">**/s**</span><span class="sxs-lookup"><span data-stu-id="69ea6-171">**/s**</span></span>|<span data-ttu-id="69ea6-172">인증서 저장소가 시스템 저장소임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-172">Indicates that the certificate store is a system store.</span></span> <span data-ttu-id="69ea6-173">이 옵션을 지정하지 않으면 저장소가 **StoreFile** 로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-173">If you do not specify this option, the store is considered to be a **StoreFile**.</span></span>|  
|<span data-ttu-id="69ea6-174">**/sha1** *sha1Hash*</span><span class="sxs-lookup"><span data-stu-id="69ea6-174">**/sha1** *sha1Hash*</span></span>|<span data-ttu-id="69ea6-175">추가, 삭제 또는 저장할 인증서, CTL 또는 CRL의 SHA1 해시를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-175">Specifies the SHA1 hash of the certificate, CTL, or CRL to add, delete, or save.</span></span>|  
|<span data-ttu-id="69ea6-176">**/v**</span><span class="sxs-lookup"><span data-stu-id="69ea6-176">**/v**</span></span>|<span data-ttu-id="69ea6-177">세부 정보 표시 모드를 지정합니다. 즉, 인증서, CTL 및 CRL에 대한 자세한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-177">Specifies verbose mode; displays detailed information about certificates, CTLs, and CRLs.</span></span> <span data-ttu-id="69ea6-178">이 옵션은 **/add**, **/del** 또는 **/put** 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-178">This option cannot be used with the **/add**, **/del**, or **/put** options.</span></span>|  
|<span data-ttu-id="69ea6-179">**/y** *provider*</span><span class="sxs-lookup"><span data-stu-id="69ea6-179">**/y** *provider*</span></span>|<span data-ttu-id="69ea6-180">저장소 공급자의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-180">Specifies the store provider name.</span></span>|  
|<span data-ttu-id="69ea6-181">**/7**</span><span class="sxs-lookup"><span data-stu-id="69ea6-181">**/7**</span></span>|<span data-ttu-id="69ea6-182">대상 저장소를 PKCS #7 개체로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-182">Saves the destination store as a PKCS #7 object.</span></span>|  
|<span data-ttu-id="69ea6-183">**/?**</span><span class="sxs-lookup"><span data-stu-id="69ea6-183">**/?**</span></span>|<span data-ttu-id="69ea6-184">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-184">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69ea6-185">설명</span><span class="sxs-lookup"><span data-stu-id="69ea6-185">Remarks</span></span>  

 <span data-ttu-id="69ea6-186">Certmgr.exe를 사용하여 다음과 같은 기본 기능을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-186">Certmgr.exe performs the following basic functions:</span></span>  
  
- <span data-ttu-id="69ea6-187">인증서, CTL 및 CRL을 콘솔에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-187">Displays certificates, CTLs, and CRLs to the console.</span></span>  
  
- <span data-ttu-id="69ea6-188">인증서, CTL 및 CRL을 인증서 저장소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-188">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>  
  
- <span data-ttu-id="69ea6-189">인증서, CTL 및 CRL을 인증서 저장소에서 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-189">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>  
  
- <span data-ttu-id="69ea6-190">인증서 저장소의 X.509 인증서, CTL 또는 CRL을 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-190">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span>  
  
 <span data-ttu-id="69ea6-191">Certmgr.exe를 사용하면 다음과 같은 두 가지 형식의 인증서 저장소를 사용하여 작업할 수 있습니다. **StoreFile** 및 시스템 저장소.</span><span class="sxs-lookup"><span data-stu-id="69ea6-191">Certmgr.exe works with two types of certificate stores: **StoreFile** and system store.</span></span> <span data-ttu-id="69ea6-192">그러나 Certmgr.exe로 저장소 형식을 식별한 다음 적합한 작업을 수행할 수 있으므로 인증서 저장소 형식을 지정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-192">It is not necessary to specify the type of certificate store; Certmgr.exe can identify the store type and perform the appropriate operations.</span></span>  
  
 <span data-ttu-id="69ea6-193">옵션을 지정하지 않고 Certmgr.exe를 실행하면 명령줄에서도 사용할 수 있는 인증서 관리 작업을 돕는 GUI인 certmgr.msc snap-in이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-193">Running Certmgr.exe without specifying any options launches the certmgr.msc snap-in, which has a GUI that helps with the certificate management tasks that are also available from the command line.</span></span> <span data-ttu-id="69ea6-194">이 GUI를 통해 디스크의 인증서, CTL 및 CRL을 인증서 저장소에 복사하는 가져오기 마법사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-194">The GUI provides an import wizard, which copies certificates, CTLs, and CRLs from your disk to a certificate store.</span></span>  
  
 <span data-ttu-id="69ea6-195">`sourceStorename` 및 `destinationStorename` 매개 변수에 대한 X509Certificate 저장소의 이름을 다음 코드를 컴파일 및 실행하여 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-195">You can find the names of X509Certificate stores for the `sourceStorename` and `destinationStorename` parameters by compiling and running the following code.</span></span>  
  
 [!code-csharp[Tools.CertMgr#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tools.certmgr/cs/storenames1.cs#1)]
 [!code-vb[Tools.CertMgr#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tools.certmgr/vb/storenames1.vb#1)]  
  
 <span data-ttu-id="69ea6-196">자세한 내용은 [인증서 작업](../wcf/feature-details/working-with-certificates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69ea6-196">For more information about certificates, see [Working with Certificates](../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="69ea6-197">예</span><span class="sxs-lookup"><span data-stu-id="69ea6-197">Examples</span></span>  

 <span data-ttu-id="69ea6-198">다음 명령을 사용하여 `my`라는 기본 시스템 저장소를 자세한 정보와 함께 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-198">The following command displays a default system store called `my` with verbose output.</span></span>  
  
```console  
certmgr /v /s my  
```  
  
 <span data-ttu-id="69ea6-199">다음 명령을 사용하여 `myFile.ext`라는 파일에 있는 모든 인증서를 `newFile.ext`라는 새 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-199">The following command adds all the certificates in a file called `myFile.ext` to a new file called `newFile.ext`.</span></span>  
  
```console  
certmgr /add /all /c myFile.ext newFile.ext  
```  
  
 <span data-ttu-id="69ea6-200">다음 명령은 `testcert.cer`이라는 파일의 인증서를 `my` 시스템 저장소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-200">The following command adds the certificate in a file named `testcert.cer` to the `my` system store.</span></span>  
  
```console  
certmgr /add /c testcert.cer /s my  
```  
  
 <span data-ttu-id="69ea6-201">다음 명령은 `TrustedCert.cer`이라는 파일의 인증서를 루트 인증서 저장소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-201">The following command adds the certificate in a file named `TrustedCert.cer` to the root certificate store.</span></span>  
  
```console  
certmgr /c /add TrustedCert.cer /s root  
```  
  
 <span data-ttu-id="69ea6-202">다음 명령을 사용하여 `myCert`시스템 저장소에 있는 `my`라는 일반 이름의 인증서를 `newCert.cer`이라는 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-202">The following command saves a certificate with the common name `myCert` in the `my` system store to a file called `newCert.cer`.</span></span>  
  
```console  
certmgr /add /c /n myCert /s my newCert.cer  
```  
  
 <span data-ttu-id="69ea6-203">다음 명령을 사용하여 `my` 시스템 저장소에 있는 모든 CTL을 삭제하고 그 결과로 만들어지는 저장소를 `newStore.str`이라는 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-203">The following command deletes all CTLs in the `my` system store and saves the resulting store to a file called `newStore.str`.</span></span>  
  
```console  
certmgr /del /all /ctl /s my newStore.str  
```  
  
 <span data-ttu-id="69ea6-204">다음 명령을 사용하여 `my`시스템 저장소의 인증서를 `newFile` 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-204">The following command saves a certificate in the `my` system store in the file `newFile`.</span></span> <span data-ttu-id="69ea6-205">그러면 `my`에 넣을 `newFile`의 인증서 번호를 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="69ea6-205">You will be prompted to enter the certificate number from `my` to put in `newFile`.</span></span>  
  
```console  
certmgr /put /c /s my newFile  
```  
  
## <a name="see-also"></a><span data-ttu-id="69ea6-206">참조</span><span class="sxs-lookup"><span data-stu-id="69ea6-206">See also</span></span>

- [<span data-ttu-id="69ea6-207">도구</span><span class="sxs-lookup"><span data-stu-id="69ea6-207">Tools</span></span>](index.md)
- [<span data-ttu-id="69ea6-208">Makecert.exe(인증서 작성 도구)</span><span class="sxs-lookup"><span data-stu-id="69ea6-208">Makecert.exe (Certificate Creation Tool)</span></span>](/windows/desktop/SecCrypto/makecert)
- [<span data-ttu-id="69ea6-209">개발자 명령줄 셸</span><span class="sxs-lookup"><span data-stu-id="69ea6-209">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)

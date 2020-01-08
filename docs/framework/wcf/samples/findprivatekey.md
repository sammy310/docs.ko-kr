---
title: FindPrivateKey 샘플
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: 0ed1e5e81a5d2f7f3586e5dce306e8244b5ebd48
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346012"
---
# <a name="findprivatekey-sample"></a><span data-ttu-id="88ee9-102">FindPrivateKey 샘플</span><span class="sxs-lookup"><span data-stu-id="88ee9-102">FindPrivateKey sample</span></span>

<span data-ttu-id="88ee9-103">인증서 저장소에서 특정 X.509 인증서와 연결된 프라이빗 키 파일의 위치 및 이름을 찾기가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-103">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="88ee9-104">FindPrivateKey.exe 도구는 이 과정에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-104">The FindPrivateKey.exe tool facilitates this process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="88ee9-105">FindPrivateKey는 사용하기 전에 컴파일되어야 하는 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-105">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="88ee9-106">FindPrivateKey 도구를 빌드하는 방법에 대 한 지침은 [FindPrivateKey 프로젝트를 빌드하](#to-build-the-findprivatekey-project) 는 방법 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="88ee9-106">See the [To build the FindPrivateKey project](#to-build-the-findprivatekey-project) section for instructions on how to build the FindPrivateKey tool.</span></span>

<span data-ttu-id="88ee9-107">X.509 인증서는 관리자 또는 시스템에 있는 모든 사용자가 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-107">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="88ee9-108">그러나 다른 계정으로 실행 되는 서비스에서 인증서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-108">However, the certificate may be accessed by a service running under a different account.</span></span> <span data-ttu-id="88ee9-109">예를 들어 네트워크 서비스 계정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-109">For example, the NETWORK SERVICE account.</span></span>

<span data-ttu-id="88ee9-110">처음에 인증서를 이 계정으로 설치하지 않았기 때문에 이 계정에 프라이빗 키 파일에 대한 액세스 권한이 없을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-110">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="88ee9-111">FindPrivateKey 도구는 지정된 X.509 인증서의 프라이빗 키 파일 위치를 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-111">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="88ee9-112">특정 X.509 인증서의 프라이빗 키 파일 위치를 알고 나면 이 파일의 사용 권한을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-112">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>

<span data-ttu-id="88ee9-113">보안을 위해 인증서를 사용 하는 샘플은 *설치 .bat* 파일의 FindPrivateKey 도구를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-113">The samples that use certificates for security use the FindPrivateKey tool in the *Setup.bat* file.</span></span> <span data-ttu-id="88ee9-114">개인 키 파일이 발견 되 면 *cacls.exe* 와 같은 다른 도구를 사용 하 여 파일에 대 한 적절 한 액세스 권한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-114">Once the private key file has been found, you can use other tools such as *Cacls.exe* to set the appropriate access rights onto the file.</span></span>

<span data-ttu-id="88ee9-115">사용자 계정 (예: 자체 호스팅 실행 파일)에서 WCF (Windows Communication Foundation) 서비스를 실행 하는 경우 사용자 계정에 파일에 대 한 읽기 전용 액세스 권한이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-115">When running a Windows Communication Foundation (WCF) service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="88ee9-116">인터넷 정보 서비스 (IIS)에서 WCF 서비스를 실행 하는 경우 서비스를 실행 하는 기본 계정은 IIS 7 및 이전 버전의 네트워크 서비스 이거나 IIS 7.5 이상 버전의 응용 프로그램 풀 Id입니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-116">When running a WCF service under Internet Information Services (IIS) the default accounts that the service runs under are the NETWORK SERVICE on IIS 7 and earlier versions, or Application Pool Identity on IIS 7.5 and later versions.</span></span> <span data-ttu-id="88ee9-117">자세한 내용은 [응용 프로그램 풀 id](/iis/manage/configuring-security/application-pool-identities)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="88ee9-117">For more information, see [Application Pool Identities](/iis/manage/configuring-security/application-pool-identities).</span></span>

## <a name="examples"></a><span data-ttu-id="88ee9-118">예</span><span class="sxs-lookup"><span data-stu-id="88ee9-118">Examples</span></span>

<span data-ttu-id="88ee9-119">프로세스에 읽기 권한이 없는 인증서에 액세스 하는 경우 다음 예제와 비슷한 예외 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-119">When accessing a certificate for which the process doesn't have read privilege, you see an exception message similar to the following example:</span></span>

```output
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

<span data-ttu-id="88ee9-120">이 문제가 발생 하는 경우 FindPrivateKey 도구를 사용 하 여 개인 키 파일을 찾은 다음 서비스가 실행 되 고 있는 프로세스에 대 한 액세스 권한을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-120">When this occurs, use the FindPrivateKey tool to find the private key file, and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="88ee9-121">예를 들어 다음 예제와 같이 Cacls.exe 도구를 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-121">For example, this can be done with the Cacls.exe tool as shown in the following example:</span></span>

```console
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="88ee9-122">FindPrivateKey 프로젝트를 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="88ee9-122">To build the FindPrivateKey project</span></span>

<span data-ttu-id="88ee9-123">프로젝트를 다운로드 하려면 [.NET Framework 4에 대 한 Windows Communication Foundation (WCF) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="88ee9-123">To download the project, visit [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span></span>

1. <span data-ttu-id="88ee9-124">파일 탐색기를 열고 샘플을 설치한 디렉터리 위치 아래의 *WF_WCF_Samples \wcf\setup\findprivatekey\cs* 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-124">Open File Explorer and navigate to the *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* folder under the directory location where you installed the sample.</span></span>

2. <span data-ttu-id="88ee9-125">.sln 파일 아이콘을 두 번 클릭하여 Visual Studio에서 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-125">Double-click the .sln file icon to open the file in Visual Studio.</span></span>

3. <span data-ttu-id="88ee9-126">**빌드** 메뉴에서 **솔루션 다시 빌드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-126">In the **Build** menu, select **Rebuild Solution**.</span></span>

4. <span data-ttu-id="88ee9-127">솔루션을 빌드하면 FindPrivateKey.exe 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-127">Building the solution generates the file: FindPrivateKey.exe.</span></span>

## <a name="conventionscommand-line-entries"></a><span data-ttu-id="88ee9-128">규칙-명령줄 항목</span><span class="sxs-lookup"><span data-stu-id="88ee9-128">Conventions—Command-Line entries</span></span>

 <span data-ttu-id="88ee9-129">"[*option*]"은 선택적 매개 변수 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-129">"[*option*]" represents an optional set of parameters.</span></span>

 <span data-ttu-id="88ee9-130">"{*option*}"은 (는) 필수 매개 변수 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-130">"{*option*}" represents a mandatory set of parameters.</span></span>

 <span data-ttu-id="88ee9-131">"*옵션 1 마이그레이션* &#124; *옵션 2 마이그레이션*"는 옵션 집합 사이의 선택을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-131">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>

 <span data-ttu-id="88ee9-132">"\<*값*>"는 입력할 매개 변수 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-132">"\<*value*>" represents a parameter value to be entered.</span></span>

## <a name="usage"></a><span data-ttu-id="88ee9-133">용도</span><span class="sxs-lookup"><span data-stu-id="88ee9-133">Usage</span></span>

```console
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

<span data-ttu-id="88ee9-134">조건:</span><span class="sxs-lookup"><span data-stu-id="88ee9-134">Where:</span></span>

| <span data-ttu-id="88ee9-135">매개 변수</span><span class="sxs-lookup"><span data-stu-id="88ee9-135">Parameter</span></span>         | <span data-ttu-id="88ee9-136">설명</span><span class="sxs-lookup"><span data-stu-id="88ee9-136">Description</span></span>                                                                       |
|-----------------|-----------------------------------------------------------------------------------|
| `<subjectName>` | <span data-ttu-id="88ee9-137">인증서의 주체 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-137">The subject name of the certificate</span></span>                                               |
| `<thumbprint>`  | <span data-ttu-id="88ee9-138">인증서의 손 도장 (Certmgr.exe 도구를 사용 하 여 찾을 수 있음)</span><span class="sxs-lookup"><span data-stu-id="88ee9-138">The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)</span></span> |
| `-f`            | <span data-ttu-id="88ee9-139">출력 파일 이름만</span><span class="sxs-lookup"><span data-stu-id="88ee9-139">output file name only</span></span>                                                             |
| `-d`            | <span data-ttu-id="88ee9-140">출력 디렉터리만</span><span class="sxs-lookup"><span data-stu-id="88ee9-140">output directory only</span></span>                                                             |
| `-a`            | <span data-ttu-id="88ee9-141">출력 절대 파일 이름</span><span class="sxs-lookup"><span data-stu-id="88ee9-141">output absolute file name</span></span>                                                         |

<span data-ttu-id="88ee9-142">명령 프롬프트에서 매개 변수를 지정 하지 않으면이 정보를 포함 하는 도움말 텍스트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-142">If no parameters are specified at the command prompt, then help text with this information is displayed.</span></span>

## <a name="examples"></a><span data-ttu-id="88ee9-143">예</span><span class="sxs-lookup"><span data-stu-id="88ee9-143">Examples</span></span>

<span data-ttu-id="88ee9-144">이 예에서는 현재 사용자의 개인 저장소에서 주체 이름이 "CN = localhost" 인 인증서의 파일 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-144">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.</span></span>

```console
FindPrivateKey My CurrentUser -n "CN=localhost"
```

<span data-ttu-id="88ee9-145">이 예제에서는 현재 사용자의 개인 저장소에서 주체 이름이 "CN = localhost" 인 인증서의 파일 이름을 찾고 전체 디렉터리 경로를 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-145">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User and output the full directory path.</span></span>

```console
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

<span data-ttu-id="88ee9-146">이 예제에서는 로컬 컴퓨터의 개인 저장소에서 지문이 "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"인 인증서의 파일 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="88ee9-146">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>

```console
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```

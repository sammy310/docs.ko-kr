---
title: '방법: SSL 인증서를 사용하여 포트 구성'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
ms.openlocfilehash: 90d5424e12bb770dc3da85e1b2738206f4777c0c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185103"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a><span data-ttu-id="724ed-102">방법: SSL 인증서를 사용하여 포트 구성</span><span class="sxs-lookup"><span data-stu-id="724ed-102">How to: Configure a Port with an SSL Certificate</span></span>

<span data-ttu-id="724ed-103">전송 보안을 사용하는 <xref:System.ServiceModel.WSHttpBinding> 클래스를 사용하여 자체 호스팅된 WCF(Windows 통신 재단) 서비스를 만들 때X.509 인증서를 사용하여 포트를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-103">When creating a self-hosted Windows Communication Foundation (WCF) service with the <xref:System.ServiceModel.WSHttpBinding> class that uses transport security, you must also configure a port with an X.509 certificate.</span></span> <span data-ttu-id="724ed-104">자체 호스트된 서비스를 만들지 않는 경우에는 IIS(인터넷 정보 서비스)에서 서비스를 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-104">If you are not creating a self-hosted service, you can host your service on Internet Information Services (IIS).</span></span> <span data-ttu-id="724ed-105">자세한 내용은 [HTTP 전송 보안을](../../../../docs/framework/wcf/feature-details/http-transport-security.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="724ed-105">For more information, see [HTTP Transport Security](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span></span>  
  
 <span data-ttu-id="724ed-106">포트를 구성하려면 컴퓨터에서 실행하는 운영 체제에 따라 다른 도구를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-106">To configure a port, the tool you use depends on the operating system that is running on your machine.</span></span>  
  
 <span data-ttu-id="724ed-107">Windows Server 2003을 실행하는 경우 HttpCfg.exe 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-107">If you are running Windows Server 2003, use the HttpCfg.exe tool.</span></span> <span data-ttu-id="724ed-108">Windows Server 2003에서 이 도구가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-108">On Windows Server 2003, this tool is installed.</span></span> <span data-ttu-id="724ed-109">자세한 내용은 [Httpcfg 개요를](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10))참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="724ed-109">For more information, see [Httpcfg Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)).</span></span> <span data-ttu-id="724ed-110">[Windows 지원 도구 설명서에서](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) Httpcfg.exe 도구에 대한 구문을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-110">The [Windows Support Tools documentation](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) explains the syntax for the Httpcfg.exe tool.</span></span>  
  
 <span data-ttu-id="724ed-111">Windows Vista를 실행하는 경우 이미 설치된 Netsh.exe 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-111">If you are running Windows Vista, use the Netsh.exe tool that is already installed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="724ed-112">컴퓨터에 저장된 인증서를 수정하려면 관리 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-112">Modifying certificates stored on the computer requires administrative privileges.</span></span>  
  
## <a name="determine-how-ports-are-configured"></a><span data-ttu-id="724ed-113">포트 구성 방법 결정</span><span class="sxs-lookup"><span data-stu-id="724ed-113">Determine how ports are configured</span></span>  
  
1. <span data-ttu-id="724ed-114">Windows Server 2003 또는 Windows XP에서 HttpCfg.exe 도구를 사용하여 다음 예제와 같이 **쿼리** 및 **ssl** 스위치를 사용하여 현재 포트 구성을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-114">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool to view the current port configuration, using the **query** and **ssl** switches, as shown in the following example.</span></span>  
  
    ```console
    httpcfg query ssl  
    ```  
  
2. <span data-ttu-id="724ed-115">Windows Vista에서 Netsh.exe 도구를 사용하여 다음 예제와 같이 현재 포트 구성을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-115">In Windows Vista, use the Netsh.exe tool to view the current port configuration, as shown in the following example.</span></span>  
  
    ```console  
    netsh http show sslcert  
    ```  
  
## <a name="get-a-certificates-thumbprint"></a><span data-ttu-id="724ed-116">인증서 지문 받기</span><span class="sxs-lookup"><span data-stu-id="724ed-116">Get a certificate's thumbprint</span></span>  
  
1. <span data-ttu-id="724ed-117">인증서 MMC 스냅인을 사용하여 클라이언트 인증 용도의 X.509 인증서를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-117">Use the Certificates MMC snap-in to find an X.509 certificate that has an intended purpose of client authentication.</span></span> <span data-ttu-id="724ed-118">자세한 내용은 [방법: MMC 스냅인을 사용하여 인증서 보기](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="724ed-118">For more information, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2. <span data-ttu-id="724ed-119">인증서의 지문에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-119">Access the certificate's thumbprint.</span></span> <span data-ttu-id="724ed-120">자세한 내용은 [방법: 인증서의 지문 검색](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="724ed-120">For more information, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
3. <span data-ttu-id="724ed-121">인증서의 지문을 메모장 등의 텍스트 편집기에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-121">Copy the thumbprint of the certificate into a text editor, such as Notepad.</span></span>  
  
4. <span data-ttu-id="724ed-122">16진수 문자 사이의 모든 공간을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-122">Remove all spaces between the hexadecimal characters.</span></span> <span data-ttu-id="724ed-123">여기에 사용되는 방법 중 하나는 텍스트 편집기의 찾기 및 바꾸기 기능을 사용하여 각 공간을 null 문자로 바꾸는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-123">One way to accomplish this is to use the text editor's find-and-replace feature and replace each space with a null character.</span></span>  
  
## <a name="bind-an-ssl-certificate-to-a-port-number"></a><span data-ttu-id="724ed-124">SSL 인증서를 포트 번호에 바인딩</span><span class="sxs-lookup"><span data-stu-id="724ed-124">Bind an SSL certificate to a port number</span></span>  
  
1. <span data-ttu-id="724ed-125">Windows Server 2003 또는 Windows XP에서 SSL(보안 소켓 계층) 저장소의 "설정" 모드에서 HttpCfg.exe 도구를 사용하여 인증서를 포트 번호에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-125">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool in "set" mode on the Secure Sockets Layer (SSL) store to bind the certificate to a port number.</span></span> <span data-ttu-id="724ed-126">도구에서는 다음 예제처럼 지문을 사용하여 인증서를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-126">The tool uses the thumbprint to identify the certificate, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - <span data-ttu-id="724ed-127">**-i** 스위치에는 : `IP``port` 구문이 있으며 인증서를 컴퓨터의 포트 8012로 설정하도록 도구에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-127">The **-i** switch has the syntax of `IP`:`port` and instructs the tool to set the certificate to port 8012 of the computer.</span></span> <span data-ttu-id="724ed-128">선택적으로, 번호 앞에 있는 4개의 0을 컴퓨터의 실제 IP 주소로 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-128">Optionally, the four zeroes that precede the number can also be replaced by the actual IP address of the computer.</span></span>  
  
    - <span data-ttu-id="724ed-129">**-h** 스위치는 인증서의 지문을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-129">The **-h** switch specifies the thumbprint of the certificate.</span></span>  
  
2. <span data-ttu-id="724ed-130">Windows Vista에서는 다음 예제와 같이 Netsh.exe 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-130">In Windows Vista, use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}
    ```  
  
    - <span data-ttu-id="724ed-131">**certhash** 매개 변수는 인증서의 지문을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-131">The **certhash** parameter specifies the thumbprint of the certificate.</span></span>  
  
    - <span data-ttu-id="724ed-132">**ipport** 매개 변수는 IP 주소와 포트를 지정하고 설명한 Httpcfg.exe 도구의 **-i** 스위치와 같은 기능을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-132">The **ipport** parameter specifies the IP address and port, and functions just like the **-i** switch of the Httpcfg.exe tool described.</span></span>  
  
    - <span data-ttu-id="724ed-133">**appid** 매개 변수는 소유 응용 프로그램을 식별하는 데 사용할 수 있는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-133">The **appid** parameter is a GUID that can be used to identify the owning application.</span></span>  
  
## <a name="bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a><span data-ttu-id="724ed-134">SSL 인증서를 포트 번호에 바인딩하고 클라이언트 인증서를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-134">Bind an SSL certificate to a port number and support client certificates</span></span>  
  
1. <span data-ttu-id="724ed-135">전송 계층에서 X.509 인증서로 인증하는 클라이언트를 지원하기 위해 Windows Server 2003 또는 Windows XP에서는 다음 예제와 같이 이전 절차를 따르지만 추가 명령줄 매개 변수를 HttpCfg.exe에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-135">In Windows Server 2003 or Windows XP, to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure but pass an additional command-line parameter to HttpCfg.exe, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     <span data-ttu-id="724ed-136">**-f** 스위치에는 n이 `n` 1과 7 사이의 숫자인 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-136">The **-f** switch has the syntax of `n` where n is a number between 1 and 7.</span></span> <span data-ttu-id="724ed-137">위의 예제와 같이 값 2를 사용하면 전송 계층에서 클라이언트 인증서가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-137">A value of 2, as shown in the preceding example, enables client certificates at the transport layer.</span></span> <span data-ttu-id="724ed-138">값 3을 사용하면 클라이언트 인증서가 활성화되고 해당 인증서가 Windows 계정에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-138">A value of 3 enables client certificates and maps those certificates to a Windows account.</span></span> <span data-ttu-id="724ed-139">다른 값의 동작에 대한 자세한 내용은 HttpCfg.exe 도움말을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="724ed-139">See HttpCfg.exe Help for the behavior of other values.</span></span>  
  
2. <span data-ttu-id="724ed-140">Windows Vista에서는 전송 계층에서 X.509 인증서로 인증하는 클라이언트를 지원하려면 다음 예제와 같이 위의 절차를 따르지만 추가 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-140">In Windows Vista, to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure, but with an additional parameter, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
## <a name="delete-an-ssl-certificate-from-a-port-number"></a><span data-ttu-id="724ed-141">포트 번호에서 SSL 인증서 삭제</span><span class="sxs-lookup"><span data-stu-id="724ed-141">Delete an SSL certificate from a port number</span></span>  
  
1. <span data-ttu-id="724ed-142">HttpCfg.exe 또는 Netsh.exe 도구를 사용하여 컴퓨터에 있는 모든 바인딩의 포트와 지문을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-142">Use the HttpCfg.exe or Netsh.exe tool to see the ports and thumbprints of all bindings on the computer.</span></span> <span data-ttu-id="724ed-143">디스크에 정보를 인쇄하려면 다음 예제와 같이 리디렉션 문자 ">"를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-143">To print the information to disk, use the redirection character ">", as shown in the following example.</span></span>  
  
    ```console  
    httpcfg query ssl>myMachinePorts.txt  
    ```
  
2. <span data-ttu-id="724ed-144">Windows Server 2003 또는 Windows XP에서 **삭제** 및 **ssl** 키워드와 함께 HttpCfg.exe 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-144">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool with the **delete** and **ssl** keywords.</span></span> <span data-ttu-id="724ed-145">**-i** 스위치를 사용하여 `IP`:`port` 번호 및 **-h** 스위치를 지정하여 지문을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-145">Use the **-i** switch to specify the `IP`:`port` number, and the **-h** switch to specify the thumbprint.</span></span>  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. <span data-ttu-id="724ed-146">Windows Vista에서는 다음 예제와 같이 Netsh.exe 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-146">In Windows Vista, use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a><span data-ttu-id="724ed-147">예제</span><span class="sxs-lookup"><span data-stu-id="724ed-147">Example</span></span>  

 <span data-ttu-id="724ed-148">다음 코드에서는 전송 보안에 설정된 <xref:System.ServiceModel.WSHttpBinding> 클래스를 사용하여 자체 호스트된 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-148">The following code shows how to create a self-hosted service using the <xref:System.ServiceModel.WSHttpBinding> class set to transport security.</span></span> <span data-ttu-id="724ed-149">애플리케이션을 만들 때에는 주소에 포트 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="724ed-149">When creating an application, specify the port number in the address.</span></span>  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="724ed-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="724ed-150">See also</span></span>

- [<span data-ttu-id="724ed-151">HTTP 전송 보안</span><span class="sxs-lookup"><span data-stu-id="724ed-151">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)

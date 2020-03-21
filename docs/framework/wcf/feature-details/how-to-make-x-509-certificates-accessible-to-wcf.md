---
title: '방법: WCF에서 X.509 인증서에 액세스할 수 있도록 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- X.509 certificates [WCF]
- certificates [WCF], making X.509 certificates accessible to WCF
- X.509 certificates [WCF], making accessible to WCF
ms.assetid: a54e407c-c2b5-4319-a648-60e43413664b
ms.openlocfilehash: 14f2242ab55795c74fa169382fef846bc0e60ace
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184904"
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a>방법: WCF에서 X.509 인증서에 액세스할 수 있도록 설정
WCF(Windows 통신 재단)에서 X.509 인증서에 액세스할 수 있도록 하려면 응용 프로그램 코드에서 인증서 저장소 이름과 위치를 지정해야 합니다. 상황에 따라, X.509 인증서와 연결된 프라이빗 키를 포함하는 파일에 대한 액세스가 프로세스 ID에 필요할 수 있습니다. 인증서 저장소에서 X.509 인증서와 연결된 개인 키를 얻으려면 WCF에 권한이 있어야 합니다. 기본적으로 소유자와 시스템 계정에서만 인증서의 프라이빗 키에 액세스할 수 있습니다.  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a>WCF에서 X.509 인증서에 액세스할 수 있도록 설정하려면  
  
1. WCF가 실행 중인 계정에 X.509 인증서와 연결된 개인 키가 포함된 파일에 대한 읽기 액세스 권한을 부여합니다.  
  
    1. WCF가 X.509 인증서의 개인 키에 대한 읽기 액세스가 필요한지 여부를 확인합니다.  
  
         다음 표에는 X.509 인증서를 사용하는 경우 프라이빗 키를 사용할 수 있어야 하는지 여부가 자세히 표시되어 있습니다.  
  
        |X.509 인증서 사용|프라이빗 키|  
        |---------------------------|-----------------|  
        |아웃바운드 SOAP 메시지 디지털 서명.|yes|  
        |인바운드 SOAP 메시지 서명 확인.|예|  
        |아웃바운드 SOAP 메시지 암호화.|예|  
        |인바운드 SOAP 메시지 암호 해독.|yes|  
  
    2. 인증서가 저장되는 인증서 저장소 위치와 이름을 확인합니다.  
  
         인증서가 저장되는 인증서 스토리지는 애플리케이션 코드 또는 구성에 지정됩니다. 예를 들어, 다음 예에서는 인증서 위치를 이름이 `CurrentUser`인 `My` 인증서 저장소로 지정합니다.  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3. [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) 도구를 사용하여 인증서의 개인 키가 컴퓨터에 있는 위치를 확인합니다.  
  
         [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) 도구에는 인증서 저장소 이름, 인증서 저장소 위치 및 인증서를 고유하게 식별하는 항목이 필요합니다. 도구에서는 인증서의 제목 이름이나 지문을 고유 식별자로 사용합니다. 인증서의 지문을 확인하는 방법에 대한 자세한 내용은 [인증서의 지문 검색 방법을](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)참조하십시오.  
  
         다음 코드 예제에서는 [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) 도구를 사용하여 `My` 의 `CurrentUser` 지문이 있는 저장소의 인증서에 대한 `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`개인 키의 위치를 결정합니다.  
  
        ```console
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4. WCF에서 실행 중인 계정을 확인합니다.  
  
         다음 표는 WCF가 지정된 시나리오에 대해 실행 중인 계정에 대해 자세히 설명합니다.  
  
        |시나리오|프로세스 ID|  
        |--------------|----------------------|  
        |클라이언트(콘솔 또는 WinForms 애플리케이션).|현재 로그인한 사용자.|  
        |자체 호스팅된 서비스.|현재 로그인한 사용자.|  
        |IIS 6.0(Windows 서버 2003) 또는 IIS 7.0(Windows Vista)에서 호스팅되는 서비스입니다.|NETWORK SERVICE|  
        |IIS 5.X(Windows XP)에서 호스팅되는 서비스입니다.|Machine.config 파일의 `<processModel>` 요소로 제어됩니다. 기본 계정은 ASPNET입니다.|  
  
    5. icacls.exe와 같은 도구를 사용하여 WCF가 실행 중인 계정에 대한 개인 키가 포함된 파일에 대한 읽기 액세스 권한을 부여합니다.  
  
         다음 코드 예제에서는 지정된 파일에 대한 임의 액세스 제어 목록(DACL)을 편집하여 네트워크 서비스 계정 읽기(:R) 액세스 권한을 부여합니다.  
  
        ```console
        icacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /grant "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a>참고 항목

- [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)
- [방법: 인증서의 지문 검색](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
- [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)

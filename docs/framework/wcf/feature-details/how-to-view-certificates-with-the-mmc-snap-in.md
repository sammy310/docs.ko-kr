---
title: '방법: MMC 스냅인이 있는 인증서 보기'
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 35048c24e838c513909fae8bedcba287001f5cef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184781"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a>방법: MMC 스냅인이 있는 인증서 보기
보안 클라이언트 또는 서비스를 만들 때 [인증서를](working-with-certificates.md) 자격 증명으로 사용할 수 있습니다. 예를 들어 일반적인 자격 증명 유형은 메서드를 사용하여 만드는 X.509 인증서입니다. <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType>

Windows 시스템에서 MMC(Microsoft 관리 콘솔)로 검사할 수 있는 세 가지 유형의 인증서 저장소가 있습니다.

- 로컬 컴퓨터: 저장소는 장치에 로컬이며 장치의 모든 사용자에게 전역입니다.

- 현재 사용자: 저장소가 장치의 현재 사용자 계정에 로컬입니다.

- 서비스 계정: 저장소가 장치의 특정 서비스에 로컬입니다.

## <a name="view-certificates-in-the-mmc-snap-in"></a>MMC 스냅인에서 인증서 보기

다음 절차에서는 로컬 장치의 저장소를 검사하여 적절한 인증서를 찾는 방법을 보여 줍니다.
  
1. **시작** 메뉴에서 **실행을** 선택한 다음 *mmc*를 입력합니다.

    MMC가 나타납니다.
  
2. **파일** 메뉴에서 **스냅 추가/제거를 선택합니다.**

    **스냅인 추가 또는 제거 창이** 나타납니다.
  
3. 사용 **가능한 스냅인** 목록에서 **인증서를**선택한 다음 **을 선택합니다.**  

    ![인증서 스냅인 추가](./media/mmc-add-certificate-snap-in.png)
  
4. 인증서 **스냅인** 창에서 컴퓨터 **계정을**선택한 다음 **다음**을 선택합니다.
  
    선택적으로 특정 서비스에 대한 현재 사용자 또는 서비스 계정에 대한 **내 사용자** **계정을** 선택할 수 있습니다.

    > [!NOTE]
    > 기기의 관리자가 아닌 경우 사용자 계정에 대해서만 인증서를 관리할 수 있습니다.
  
5. 컴퓨터 **선택** 창에서 **로컬 컴퓨터를** 선택한 다음 **완료를**선택합니다.  
  
6. **스냅인 추가 또는 제거** 창에서 **확인을**선택합니다.  
  
    ![인증서 스냅인 추가](./media/mmc-certificate-snap-in-selected.png)

7. 선택 사항: **파일** 메뉴에서 **저장** 또는 **저장을** 선택하여 나중에 사용할 수 있도록 MMC 콘솔 파일을 저장합니다.  

8. MMC 스냅인에서 인증서를 보려면 왼쪽 창에서 **콘솔 루트를** 선택한 다음 **인증서(로컬 컴퓨터)를 확장합니다.**

    각 인증서 유형에 대한 디렉터리 목록이 나타납니다. 각 인증서 디렉터리에서 해당 인증서를 보고, 내보내고, 가져오고, 삭제할 수 있습니다.

## <a name="view-certificates-with-the-certificate-manager-tool"></a>인증서 관리자 도구를 사용하여 인증서 보기

인증서 관리자 도구를 사용하여 인증서를 보고, 내보내고, 가져오고, 삭제할 수도 있습니다.

### <a name="to-view-certificates-for-the-local-device"></a>로컬 장치에 대한 인증서를 보려면

1. **시작** 메뉴에서 **실행을** 선택한 다음 *certlm.msc를*입력합니다.

    로컬 장치에 대한 인증서 관리자 도구가 나타납니다.
  
2. 인증서를 보려면 인증서 **-** 왼쪽 창에 있는 로컬 컴퓨터 아래에서 보려는 인증서 유형에 대한 디렉터리를 확장합니다.

### <a name="to-view-certificates-for-the-current-user"></a>현재 사용자의 인증서를 보려면

1. **시작** 메뉴에서 **실행을** 선택한 다음 *certmgr.msc를*입력합니다.

    현재 사용자의 인증서 관리자 도구가 나타납니다.
  
2. 인증서를 보려면 인증서 **-** 왼쪽 창의 현재 사용자 아래에서 보려는 인증서 유형에 대한 디렉터리를 확장합니다.

## <a name="see-also"></a>참고 항목

- [인증서 작업](working-with-certificates.md)
- [방법: 개발 중에 사용할 임시 인증서 만들기](how-to-create-temporary-certificates-for-use-during-development.md)
- [방법: 인증서의 지문 검색](how-to-retrieve-the-thumbprint-of-a-certificate.md)

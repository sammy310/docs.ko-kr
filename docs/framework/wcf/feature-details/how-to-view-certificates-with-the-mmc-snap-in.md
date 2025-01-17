---
title: '방법: MMC 스냅인을 사용 하 여 인증서 보기'
description: 보안 WCF 클라이언트 또는 서비스는 인증서를 자격 증명으로 사용할 수 있습니다. MMC 플러그 인을 사용 하 여 검사할 수 있는 인증서 저장소의 유형에 대해 알아봅니다.
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 788161db2e38dc942b0c638128f8599b0436c8fd
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604582"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a>방법: MMC 스냅인을 사용 하 여 인증서 보기

보안 클라이언트 또는 서비스를 만들 때 [인증서](working-with-certificates.md) 를 자격 증명으로 사용할 수 있습니다. 예를 들어 일반적인 자격 증명 형식은 x.509 인증서 이며 메서드를 사용 하 여 만듭니다 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> .

Windows 시스템에서 MMC (Microsoft Management Console)를 사용 하 여 검사할 수 있는 인증서 저장소에는 다음 세 가지 유형이 있습니다.

- 로컬 컴퓨터: 저장소는 장치에 대해 로컬 이며 장치의 모든 사용자에 게 전역입니다.

- 현재 사용자: 스토어는 장치의 현재 사용자 계정에 대해 로컬입니다.

- 서비스 계정: 저장소는 장치의 특정 서비스에 대해 로컬입니다.

## <a name="view-certificates-in-the-mmc-snap-in"></a>MMC 스냅인에서 인증서 보기

다음 절차에서는 로컬 장치에서 저장소를 검사 하 여 적절 한 인증서를 찾는 방법을 보여 줍니다.
  
1. **시작** 메뉴에서 **실행** 을 선택한 다음 *mmc* 를 입력 합니다.

    MMC가 나타납니다.
  
2. **파일** 메뉴에서 **스냅인 추가/제거** 를 선택 합니다.

    **스냅인 추가/제거** 창이 나타납니다.
  
3. **사용 가능한 스냅인** 목록에서 **인증서** 를 선택 하 고 **추가** 를 선택 합니다.  

    ![인증서 스냅인 추가](./media/mmc-add-certificate-snap-in.png)
  
4. **인증서 스냅인** 창에서 **컴퓨터 계정** 을 선택 하 고 **다음** 을 선택 합니다.
  
    필요에 따라 특정 서비스에 대 한 현재 사용자 또는 **서비스 계정** 에 대해 **내 사용자 계정** 을 선택할 수 있습니다.

    > [!NOTE]
    > 사용자가 장치에 대 한 관리자가 아닌 경우 사용자 계정에 대해서만 인증서를 관리할 수 있습니다.
  
5. **컴퓨터 선택** 창에서 **로컬 컴퓨터** 를 선택 된 상태로 두고 **마침** 을 선택 합니다.  
  
6. **스냅인 추가/제거** 창에서 **확인** 을 선택 합니다.  
  
    ![확인 단추가 강조 표시 된 스냅인 추가 또는 제거](./media/mmc-certificate-snap-in-selected.png)

7. 선택 사항: **파일** 메뉴에서 **저장** 또는 **다른 이름으로 저장** 을 선택 하 여 나중에 사용할 수 있도록 MMC 콘솔 파일을 저장 합니다.  

8. MMC 스냅인에서 인증서를 보려면 왼쪽 창에서 **콘솔 루트** 를 선택한 다음 **인증서 (로컬 컴퓨터)** 를 확장 합니다.

    각 유형의 인증서에 대 한 디렉터리 목록이 표시 됩니다. 각 인증서 디렉터리에서 해당 인증서를 확인, 내보내기, 가져오기 및 삭제할 수 있습니다.

## <a name="view-certificates-with-the-certificate-manager-tool"></a>인증서 관리자 도구를 사용 하 여 인증서 보기

인증서 관리자 도구를 사용 하 여 인증서를 확인, 내보내기, 가져오기 및 삭제할 수도 있습니다.

### <a name="to-view-certificates-for-the-local-device"></a>로컬 장치에 대 한 인증서를 보려면

1. **시작** 메뉴에서 **실행** 을 선택 하 고 다음을 *입력 합니다.*

    로컬 디바이스용 인증서 관리자 도구가 표시됩니다.
  
2. 인증서를 보려면 왼쪽 창의 **인증서-로컬 컴퓨터** 에서 보려는 인증서의 유형에 해당 하는 디렉터리를 확장 합니다.

### <a name="to-view-certificates-for-the-current-user"></a>현재 사용자에 대 한 인증서를 보려면

1. **시작** 메뉴에서 **실행** 을 선택한 다음 *certmgr.exe* 를 입력 합니다.

    현재 사용자에 대 한 인증서 관리자 도구가 표시 됩니다.
  
2. 인증서를 보려면 왼쪽 창의 **인증서-현재 사용자** 에서 보려는 인증서 유형의 디렉터리를 확장 합니다.

## <a name="see-also"></a>참고 항목

- [인증서 작업](working-with-certificates.md)
- [방법: 개발 중 사용할 임시 인증서 만들기](how-to-create-temporary-certificates-for-use-during-development.md)
- [방법: 인증서의 지문 검색](how-to-retrieve-the-thumbprint-of-a-certificate.md)

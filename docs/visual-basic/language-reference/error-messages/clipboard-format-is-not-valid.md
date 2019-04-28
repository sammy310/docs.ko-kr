---
title: 클립보드 형식이 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 5ec077be30b0afc8917d431dc9bd73c8dd41be89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61649870"
---
# <a name="clipboard-format-is-not-valid"></a>클립보드 형식이 잘못되었습니다.
지정된 된 클립보드 형식 실행 중인 메서드를 사용 하 여 호환 되지 않습니다. 이 오류에 대 한 가능한 원인 중:  
  
- 클립보드의를 사용 하 여 `GetText` 또는 `SetText` 이외의 다른 클립보드 형식 사용 하 여 메서드 `vbCFText` 또는 `vbCFLink`합니다.  
  
- 클립보드의를 사용 하 여 `GetData` 또는 `SetData` 이외의 다른 클립보드 형식 사용 하 여 메서드 `vbCFBitmap`를 `vbCFDIB`, 또는 `vbCFMetafile`합니다.  
  
- 사용 하는 `GetData` 또는 `SetData` 의 메서드는 `DataObject` 등록 된 형식 (HC000-& HFFFF), Microsoft Windows에서 예약 된 범위에서를 클립보드 형식으로 때 해당 클립보드 형식을 등록 되지 않은 Microsoft Windows를 사용 하 여 .  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 잘못 된 형식을 제거 하 고 유효한을 지정 합니다.  
  
## <a name="see-also"></a>참고자료

- [클립보드: 기타 서식 추가](/cpp/mfc/clipboard-adding-other-formats)

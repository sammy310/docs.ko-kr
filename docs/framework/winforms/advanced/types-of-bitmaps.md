---
title: 비트맵의 유형
ms.date: 03/30/2017
helpviewer_keywords:
- jpeg files
- TIFF files
- gif files
- Graphics Interchange Format
- Joint Photographic Experts Group
- .jpeg files
- .gif files
- graphics [Windows Forms], file formats
- images [Windows Forms], file formats
- Portable Network Graphics
- .bmp files
- EXIF file format
- PNG files
- pictures [Windows Forms], file formats
- Tag Image File Format
- bitmaps [Windows Forms], file format
- Exchangeable Image File
ms.assetid: 6be085a2-2c13-47c8-b80a-c18b32777d8d
ms.openlocfilehash: f41585ba8816e0b1894a9f01163191848ae391e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663952"
---
# <a name="types-of-bitmaps"></a>비트맵의 유형
비트맵은 픽셀의 사각형 배열에서 각 픽셀의 색을 지정 하는 비트의 배열입니다. 각 픽셀에 사용 되는 비트 수가 해당 픽셀에 할당할 수 있는 색 수를 결정 합니다. 예를 들어, 각 픽셀을 4 비트로 표현할 경우 다음 지정된 된 픽셀 할당할 수 있습니다 다른 16 색 중 하나로 (2 ^4 = 16). 다음 표에서 지정 된 비트 수를 나타내는 픽셀에 할당할 수 있는 색 수가 몇 가지 예를 보여 줍니다.  
  
|픽셀당 비트 수|픽셀에 할당할 수 있는 색 수|  
|--------------------|------------------------------------------------------|  
|1|2^1 = 2|  
|2|2^2 = 4|  
|4|2^4 = 16|  
|8|2^8 = 256|  
|16|2^16 = 65,536|  
|24|2^24 = 16,777,216|  
  
 일반적으로 비트맵을 저장 하는 디스크 파일 배열에 있는 행의 수, 각 행에는 픽셀 수 및 픽셀당 비트 수와 같은 정보를 저장 하는 하나 이상의 정보 블록을 포함 합니다. 이러한 파일 (색상표) 색 테이블을 포함할 수도 있습니다. 색 테이블에서는 특정 색 비트맵의 번호를 매핑합니다. 다음 그림에서는 해당 비트맵 및 색 테이블 함께 확대 된 이미지를 보여 줍니다. 2 가지 픽셀당 4 비트 수를 나타내는 ^4 = 16 색상표의 색입니다. 테이블의 각 색은 24 비트 숫자로 표현 됩니다. 빨강의 8 비트, 8 비트, 초록 및 파랑 8 비트입니다. 숫자가 16 진수 (기 수 16) 폼에 표시 됩니다. A = 10, B = 11, C = 12, D = 13, E = 14, F = 15.  
  
 ![비트맵 샘플](./media/aboutgdip03-art01.gif "AboutGdip03_Art01")  
  
 3 행, 열 5 이미지의 픽셀을 살펴봅니다. 비트맵의 해당 번호가 1입니다. 색상표는 1은 빨강 픽셀은 빨간색을 알려줍니다. 비트맵의 맨 위 행의 모든 항목은 3입니다. 색상표는 이미지의 맨 위 행의 모든 픽셀은 파란색으로 표시 되므로 3은 파랑을 알려줍니다.  
  
> [!NOTE]
>  일부 비트맵 상향식 형식으로 저장 됩니다. 비트맵의 첫 번째 행의 숫자는 이미지의 아래쪽 행에 있는 픽셀에 해당 합니다.  
  
 색 테이블에 인덱스를 저장 하는 비트맵 색상표 인덱싱된 비트맵을 라고 합니다. 일부 비트맵 색 테이블에 대 한 필요가 없습니다. 예를 들어 비트맵이 픽셀당 24 비트를 사용 하면 해당 비트맵 저장할 수 있습니다 인덱스 대신 자체 색 색상표에. 다음 그림에서는 색 테이블을 사용 하는 대신 직접 색 (픽셀당 24 비트)를 저장 하는 비트맵을 보여 줍니다. 그림에는 해당 이미지의 확대 된 뷰를 보여 줍니다. 비트맵 FFFFFF은 흰색을 나타냅니다, 그리고 f f 0000 red, 00FF00 나타내는 녹색을 나타내고 0000ff은 파란색을 나타냅니다.  
  
 ![비트맵 샘플](./media/aboutgdip03-art02.gif "AboutGdip03_Art02")  
  
## <a name="graphics-file-formats"></a>그래픽 파일 형식  
 디스크 파일에 비트맵을 저장 하기 위한 다양 한 표준 형식 있습니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 그래픽 파일 형식 다음 단락에서 설명한 지원 합니다.  
  
### <a name="bmp"></a>BMP  
 BMP은 Windows 장치 및 응용 프로그램 독립적인 이미지를 저장 하기 위해 사용 하는 표준 형식입니다. 지정된 된 BMP 파일에 대 한 픽셀 (1, 4, 8, 15, 24, 32 또는 64) 당 비트 수는 파일 헤더에 지정 됩니다. 픽셀당 24 비트를 사용 하 여 BMP 파일은 공용입니다. BMP 파일은 일반적으로 압축 되지 않습니다 하 고 따라서은 적합 하지 않습니다 전송에 대 한 인터넷을 통해.  
  
### <a name="graphics-interchange-format-gif"></a>GIF(Graphics Interchange Format)  
 GIF는 웹 페이지에 표시 되는 이미지에 대 한 일반적인 형식입니다. Gif 색 간의 정확한 경계를 사용 하 여 줄 그리기, 단색 블록을 사용 하 여 사진을 그림과 적합 합니다. Gif는 압축 되지만 압축 프로세스;에 없는 정보가 손실 됩니다. 이미지를 압축 해제 된 원래와 정확히 같습니다. 이미지에 표시 하는 웹 페이지의 배경색을 갖게 됩니다 있도록 투명으로 gif 이미지에서 색을 지정할 수 있습니다. GIF 이미지 시퀀스에 관한 애니메이션된 GIF를 단일 파일에 저장할 수 있습니다. Gif 256 색으로 제한 되므로 최대 8 비트 / 픽셀을 저장 합니다.  
  
### <a name="joint-photographic-experts-group-jpeg"></a>Joint Photographic Experts Group (JPEG)  
 JPEG 압축 체계 스캔 한 사진과 같은 자연 스러운 장면을 위한 잘 작동 하는 경우 압축 프로세스에서 일부 정보가 손실 되지만 손실 육안으로 감지할 수 없는 경우가 많습니다. Jpeg 16 백만 개 색을 표시할 수 있도록, 픽셀당 24 비트를 저장 합니다. 투명도 또는 애니메이션에는 jpeg로 지원 하지 않습니다.  
  
 JPEG 이미지의 압축 수준을 구성할 수는 있지만 자세한 정보가 손실의 높은 압축 수준 (더 작은 파일). 종종 20:1 압축 비율을 다듬는 기법인 찾는 원래 구분 하기 어려운 이미지를 생성 합니다. 다음 그림에서는 BMP 이미지 및 BMP 이미지에서 압축 된 JPEG 이미지를 두 개를 보여 줍니다. 첫 번째 JPEG 압축 4:1 비율로 있고 두 번째 JPEG 압축 비율이 8:1.  
  
 ![Filetype 샘플](./media/aboutgdip03-art03.gif "AboutGdip03_Art03")  
  
 JPEG 압축 선 그리기 단색 블록에서 잘 작동 하지 않으며 경계 뾰족한 합니다. 다음 그림에서는 두 개의 Jpeg, GIF 함께 BMP를 보여 줍니다. Jpeg, GIF BMP에서 압축 되었습니다. 압축률은 더 작은 JPEG, 고 큰 JPEG 8:3 4:1 GIF, 4:1입니다. GIF 유지 하면 선 따라 날카로운 경계는 경계를 흐리게 표시 하는 jpeg로 경향이 있습니다 note 합니다.  
  
 ![Filetypes](./media/aboutgdip03-art03a.gif "AboutGdip03_Art03A")  
  
 JPEG 압축 체계를 파일 형식이 아니라는입니다. JPEG 파일 교환 형식 (JFIF)에 저장 하 고 JPEG 체계에 따라 압축 된 이미지 전송에 대 한 일반적으로 사용 되는 파일 형식입니다. 웹 브라우저에서 표시 되는 JFIF 파일.jpg 확장을 사용 합니다.  
  
### <a name="exchangeable-image-file-exif"></a>교환 이미지 파일 (EXIF)  
 EXIF는 디지털 카메라에서 찍은 사진에 사용 되는 파일 형식입니다. EXIF 파일 JPEG 사양에 따라 압축 된 이미지를 포함 합니다. EXIF 파일에 대 한 정보도 사진을 (만든 날짜, 속도, 노출 시간 등에 셔터) 및 카메라 (제조업체, 모델 및 등)에 대 한 정보입니다.  
  
### <a name="portable-network-graphics-png"></a>PNG(이동식 네트워크 그래픽)  
 PNG 형식으로 다양 한 GIF 형식의 이점을 유지 되지만 GIF를 능가 하는 기능도 제공 합니다. GIF 파일 처럼 PNG 파일 정보의 손실 없이 압축 됩니다. PNG 파일 8, 24 또는 1, 2, 4, 8을 사용 하 여 회색조 및 픽셀당 48 비트 또는 픽셀당 16 비트를 사용 하 여 색을 저장할 수 있습니다. 반면,만 1, 2, 4 또는 8 비트 / 픽셀 GIF 파일 사용할 수 있습니다. PNG 파일을 해당 픽셀의 색이 배경색과 혼합 됩니다 배경색을 사용 하 여 정도 지정 하는 각 픽셀의 알파 값을 저장할 수도 있습니다.  
  
 점진적으로 이미지를 표시 하는 능력에 GIF 향상 PNG (즉, 이미지의 더 선명 그대로 표시할 도착 하면 네트워크 연결을 통해). 다양 한 디스플레이 장치에 이미지를 정확 하 게 렌더링할 수 있도록 PNG 파일 감마 보정 및 색 수정 정보를 포함할 수 있습니다.  
  
### <a name="tag-image-file-format-tiff"></a>Tag Image File Format (TIFF)  
 TIFF는 다양 한 플랫폼 및 이미지 처리 응용 프로그램에서 지원 되는 유연 하 고 확장 가능한 형식입니다. TIFF 파일 임의 개수의 픽셀당 비트 수를 사용 하 여 이미지를 저장할 수 및 다양 한 압축 알고리즘을 사용할 수 있습니다. 여러 이미지를 여러 페이지의 단일 TIFF 파일에 저장할 수 있습니다. (작성 한 스캐너, 호스트 컴퓨터, 압축, 방향, 등에 픽셀 당 샘플 형식) 이미지와 관련 된 정보를 파일에 저장 하 고 태그를 사용 하 여 정렬 될 수 있습니다. TIFF 형식의 승인 및 새 태그를 추가 하 여 필요에 따라 확장할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Drawing.Image?displayProperty=nameWithType>
- <xref:System.Drawing.Bitmap?displayProperty=nameWithType>
- <xref:System.Drawing.Imaging.PixelFormat?displayProperty=nameWithType>
- [이미지, 비트맵 및 메타파일](images-bitmaps-and-metafiles.md)
- [이미지, 비트맵, 아이콘 및 메타파일 사용](working-with-images-bitmaps-icons-and-metafiles.md)

# 세종말뭉치 정제 데이터

세종말뭉치의 문장, 품사 부분만을 선택하여 학습용 파일로 만들었습니다. raw file로부터 [processing][processedfile]된 파일은 link로 있으며, [soynlp][soynlp]와 [classifier based noun extractor][cbne]에 이용되는 [L-R matrix 형태][lr]로 가공된 데이터도 링크로 공유합니다. 

압축되어 있는 파일을 README.md가 있는 . 폴더에서 풀면 Jupyter notebook 파일들과 경로가 맞습니다. 


## 세종 말뭉치 통계

### 어절 통계

세종 말뭉치는 구어 데이터 200개, 문어 데이터 279개로 이뤄져 있습니다. 문장 수, 어절 수, 단어 수는 아래와 같습니다. 

    문장: 216,723 (구어), 837,843 (문어)
    
구어/문어 데이터를 종합하여 존재하는 어절과 고유어절의 개수는 아래와 같습니다. 

    어절: 10,807,777
    고유 어절: 1,560,437

    Top 50 eojeols
    [('그', 81457),
    ('수', 68306),
    ('있다.', 56845),
    ('있는', 55802),
    ('이', 47680),
    ('한', 39459),
    ('것이다.', 37810),
    ('하는', 25381),
    ('것은', 24816),
    ('것이', 24642),
    ('그러나', 24511),
    ('할', 22909),
    ('나는', 22162),
    ('한다.', 21743),
    ('같은', 21198),
    ('있었다.', 20835),
    ('대한', 20529),
    ('또', 19782),
    ('그런', 19575),
    ('그리고', 18481),
    ('안', 17729),
    ('더', 17374),
    ('것을', 16830),
    ('우리', 16461),
    ('하고', 16312),
    ('그는', 15906),
    ('다른', 15238),
    ('때', 14866),
    ('없는', 14781),
    ('했다.', 14724),
    ('등', 14473),
    ('이런', 14375),
    ('두', 13645),
    ('내가', 13533),
    ('것', 13433),
    ('잘', 13230),
    ('다시', 13112),
    ('어떤', 12771),
    ('때문에', 12745),
    ('내', 12236),
    ('다', 11823),
    ('그의', 11120),
    ('것으로', 11046),
    ('없다.', 10544),
    ('이렇게', 10499),
    ('게', 10452),
    ('위해', 10374),
    ('가장', 10309),
    ('아니라', 10125),
    ('있을', 9922)]

'지금은, 지금/NNG + 은/JKS'과 같이 (어절, 단어, 품사)로 이뤄진 pair의 고유 개수는 **1,642,217** 개 입니다. 각 고유 pair와 빈도수는 [tokentable.txt][lr]에 저장되어 있습니다. 스냅샷은 아래와 같습니다. 

    ...
    예술가의	예술가/NNG+의/JKG	113
    예술가는	예술가/NNG+는/JX	45
    예술가	예술가/NNG	44
    예술가가	예술가/NNG+가/JKS	43
    예술가들의	예술가/NNG+들/XSN+의/JKG	30
    예술가들은	예술가/NNG+들/XSN+은/JX	30
    예술가들이	예술가/NNG+들/XSN+이/JKS	25
    예술가가	예술가/NNG+가/JKC	22
    ....

### 글자 통계

한국어는 1000여 글자가 자주 사용된다고 알려져 있으며, 세종 말뭉치 기준 300 글자가 89.48% 를 차지한다. 자주 이용되는 글자는 아래와 같다. 글자 옆의 수치는 (빈도수, 누적 비율)이다. 

    이 (1167221, 3.71 %), 다 (977169, 6.81 %), 는 (850962, 9.52 %), 에 (621290, 11.49 %)
    의 (609623, 13.43 %), 을 (582238, 15.28 %), 가 (551022, 17.03 %), 고 (548996, 18.77 %)
    하 (511458, 20.40 %), 지 (481319, 21.92 %), 그 (415148, 23.24 %), 한 (404041, 24.53 %)
    로 (402448, 25.81 %), 서 (389041, 27.04 %), 은 (387046, 28.27 %), 어 (364381, 29.43 %)
    기 (356798, 30.56 %), 나 (323632, 31.59 %), 도 (322734, 32.62 %), 아 (306072, 33.59 %)
    를 (304788, 34.56 %), 사 (300428, 35.51 %), 리 (278356, 36.39 %), 있 (271760, 37.26 %)
    들 (257388, 38.08 %), 자 (257294, 38.89 %), 대 (237144, 39.65 %), 으 (233996, 40.39 %)
    인 (227498, 41.11 %), 것 (227277, 41.83 %), 시 (219237, 42.53 %), 라 (213233, 43.21 %)
    게 (207331, 43.87 %), 해 (204475, 44.52 %), 수 (202083, 45.16 %), 니 (183153, 45.74 %)
    정 (175165, 46.30 %), 보 (168677, 46.83 %), 만 (167919, 47.37 %), 적 (167133, 47.90 %)
    일 (164002, 48.42 %), 면 (161772, 48.93 %), 었 (157697, 49.43 %), 과 (156109, 49.93 %)
    부 (151394, 50.41 %), 제 (150376, 50.89 %), 주 (147128, 51.35 %), 여 (138507, 51.79 %)
    전 (136390, 52.23 %), 상 (134604, 52.66 %), 장 (134567, 53.08 %), 구 (129907, 53.50 %)
    문 (127071, 53.90 %), 우 (117545, 54.27 %), 거 (115955, 54.64 %), 요 (114157, 55.00 %)
    내 (112497, 55.36 %), 되 (112424, 55.72 %), 러 (110573, 56.07 %), 성 (110331, 56.42 %)
    생 (107519, 56.76 %), 했 (107254, 57.10 %), 동 (104542, 57.43 %), 마 (104454, 57.77 %)
    무 (104355, 58.10 %), 소 (103415, 58.43 %), 국 (102545, 58.75 %), 신 (100787, 59.07 %)
    야 (95767, 59.38 %), 말 (95467, 59.68 %), 화 (94345, 59.98 %), 원 (92280, 60.27 %)
    없 (92176, 60.57 %), 데 (91305, 60.86 %), 경 (90527, 61.14 %), 스 (90482, 61.43 %)
    와 (88650, 61.71 %), 할 (88292, 61.99 %), 위 (87195, 62.27 %), 모 (87135, 62.55 %)
    오 (86909, 62.82 %), 비 (86275, 63.10 %), 학 (85530, 63.37 %), 조 (84792, 63.64 %)
    까 (82976, 63.90 %), 간 (81946, 64.16 %), 때 (81908, 64.42 %), 미 (78945, 64.67 %)
    안 (78630, 64.92 %), 중 (78532, 65.17 %), 세 (78164, 65.42 %), 려 (77567, 65.67 %)
    계 (77091, 65.91 %), 치 (75232, 66.15 %), 관 (74380, 66.39 %), 실 (73559, 66.62 %)
    진 (73391, 66.85 %), 선 (73359, 67.09 %), 음 (72630, 67.32 %), 않 (71829, 67.55 %)
    물 (70536, 67.77 %), 공 (70487, 67.99 %), 회 (70401, 68.22 %), 연 (68720, 68.44 %)
    유 (68229, 68.65 %), 개 (67140, 68.87 %), 방 (67061, 69.08 %), 교 (65495, 69.29 %)
    람 (64439, 69.49 %), 분 (64323, 69.70 %), 히 (63795, 69.90 %), 각 (63006, 70.10 %)
    며 (62988, 70.30 %), 단 (62205, 70.50 %), 식 (61769, 70.69 %), 바 (61753, 70.89 %)
    운 (61078, 71.08 %), 두 (60882, 71.28 %), 명 (60623, 71.47 %), 던 (57808, 71.65 %)
    된 (57618, 71.84 %), 당 (57249, 72.02 %), 체 (57165, 72.20 %), 등 (56337, 72.38 %)
    용 (56035, 72.56 %), 금 (55334, 72.73 %), 통 (54906, 72.91 %), 년 (54145, 73.08 %)
    발 (54043, 73.25 %), 래 (53764, 73.42 %), 같 (53649, 73.59 %), 작 (53528, 73.76 %)
    저 (52099, 73.93 %), 영 (51868, 74.09 %), 르 (51694, 74.26 %), 런 (51627, 74.42 %)
    더 (51179, 74.58 %), 산 (51106, 74.75 %), 았 (51076, 74.91 %), 민 (49046, 75.06 %)
    행 (49002, 75.22 %), 속 (48661, 75.37 %), 재 (48550, 75.53 %), 차 (48452, 75.68 %)
    터 (47125, 75.83 %), 반 (46991, 75.98 %), 입 (46869, 76.13 %), 업 (46754, 76.28 %)
    처 (46496, 76.43 %), 습 (46459, 76.57 %), 남 (45221, 76.72 %), 였 (44763, 76.86 %)
    심 (44451, 77.00 %), 건 (44150, 77.14 %), 현 (43911, 77.28 %), 결 (43501, 77.42 %)
    집 (42784, 77.55 %), 불 (42560, 77.69 %), 역 (41995, 77.82 %), 드 (40898, 77.95 %)
    직 (40354, 78.08 %), 양 (40014, 78.21 %), 예 (39944, 78.33 %), 감 (39482, 78.46 %)
    달 (38783, 78.58 %), 른 (38572, 78.71 %), 본 (38119, 78.83 %), 난 (37514, 78.95 %)
    점 (37447, 79.07 %), 또 (36928, 79.18 %), 렇 (36490, 79.30 %), 못 (35675, 79.41 %)
    력 (35087, 79.52 %), 설 (34907, 79.63 %), 형 (34506, 79.74 %), 후 (34421, 79.85 %)
    살 (34232, 79.96 %), 질 (34191, 80.07 %), 버 (34128, 80.18 %), 따 (34114, 80.29 %)
    배 (33987, 80.40 %), 날 (33745, 80.50 %), 노 (33222, 80.61 %), 근 (33153, 80.71 %)
    든 (33142, 80.82 %), 호 (33025, 80.92 %), 타 (32871, 81.03 %), 강 (32719, 81.13 %)
    느 (32059, 81.23 %), 알 (31952, 81.34 %), 법 (31357, 81.43 %), 트 (30869, 81.53 %)
    머 (30816, 81.63 %), 번 (30799, 81.73 %), 많 (30112, 81.82 %), 표 (30066, 81.92 %)
    울 (29709, 82.01 %), 태 (29643, 82.11 %), 천 (29584, 82.20 %), 겠 (29539, 82.30 %)
    종 (29414, 82.39 %), 론 (29254, 82.48 %), 편 (29049, 82.57 %), 받 (28513, 82.67 %)
    매 (28110, 82.75 %), 목 (27851, 82.84 %), 술 (27778, 82.93 %), 새 (27631, 83.02 %)
    외 (27610, 83.11 %), 파 (27551, 83.19 %), 임 (27347, 83.28 %), 함 (27319, 83.37 %)
    란 (27032, 83.45 %), 언 (26696, 83.54 %), 약 (26410, 83.62 %), 권 (26389, 83.71 %)
    피 (26115, 83.79 %), 출 (26077, 83.87 %), 돌 (26056, 83.96 %), 월 (25826, 84.04 %)
    포 (25611, 84.12 %), 럼 (25591, 84.20 %), 루 (25277, 84.28 %), 린 (24836, 84.36 %)
    녀 (24817, 84.44 %), 네 (24782, 84.52 %), 너 (24636, 84.59 %), 추 (24514, 84.67 %)
    합 (24338, 84.75 %), 디 (24275, 84.83 %), 록 (24096, 84.90 %), 석 (24072, 84.98 %)
    걸 (23946, 85.06 %), 군 (23876, 85.13 %), 절 (23604, 85.21 %), 열 (23514, 85.28 %)
    길 (23454, 85.36 %), 얼 (23349, 85.43 %), 청 (23255, 85.50 %), 활 (23150, 85.58 %)
    눈 (23141, 85.65 %), 온 (23127, 85.73 %), 져 (23002, 85.80 %), 향 (22885, 85.87 %)
    변 (22883, 85.94 %), 름 (22811, 86.02 %), 평 (22701, 86.09 %), 복 (22591, 86.16 %)
    초 (22462, 86.23 %), 잘 (22205, 86.30 %), 씨 (22201, 86.37 %), 올 (22187, 86.44 %)
    순 (22024, 86.51 %), 환 (21896, 86.58 %), 능 (21887, 86.65 %), 늘 (21692, 86.72 %)
    품 (21650, 86.79 %), 판 (21623, 86.86 %), 좋 (21602, 86.93 %), 손 (21476, 87.00 %)
    책 (21475, 87.06 %), 누 (21450, 87.13 %), 특 (21412, 87.20 %), 애 (21344, 87.27 %)
    준 (21305, 87.33 %), 크 (21299, 87.40 %), 랑 (21100, 87.47 %), 프 (21025, 87.54 %)
    증 (21025, 87.60 %), 막 (20927, 87.67 %), 레 (20862, 87.74 %), 백 (20581, 87.80 %)
    독 (20393, 87.87 %), 먹 (20285, 87.93 %), 담 (20234, 87.99 %), 박 (20227, 88.06 %)
    필 (19806, 88.12 %), 앞 (19749, 88.18 %), 참 (19711, 88.25 %), 최 (19656, 88.31 %)
    격 (19525, 88.37 %), 왔 (19480, 88.43 %), 키 (19410, 88.50 %), 급 (19238, 88.56 %)
    워 (19141, 88.62 %), 족 (19048, 88.68 %), 놓 (18891, 88.74 %), 김 (18756, 88.80 %)
    별 (18588, 88.86 %), 확 (18473, 88.92 %), 육 (18164, 88.97 %), 병 (18122, 89.03 %)
    토 (18052, 89.09 %), 쪽 (17754, 89.14 %), 님 (17686, 89.20 %), 줄 (17666, 89.26 %)
    친 (17546, 89.31 %), 될 (17383, 89.37 %), 겨 (17295, 89.42 %), 창 (17207, 89.48 %)
    잡 (17166, 89.53 %), 료 (16996, 89.59 %), 벌 (16907, 89.64 %), 듯 (16893, 89.69 %)
    련 (16749, 89.75 %), 뭐 (16747, 89.80 %), 침 (16721, 89.85 %), 갈 (16700, 89.91 %)
    뒤 (16587, 89.96 %), 쓰 (16470, 90.01 %), 죽 (16402, 90.06 %), 렸 (16247, 90.11 %)
    투 (16242, 90.17 %), 망 (16204, 90.22 %), 냐 (16126, 90.27 %), 극 (16041, 90.32 %)
    북 (15909, 90.37 %), 곳 (15867, 90.42 %), 채 (15799, 90.47 %), 철 (15433, 90.52 %)
    졌 (15366, 90.57 %), 삼 (15144, 90.62 %), 움 (15022, 90.66 %), 혼 (14873, 90.71 %)
    험 (14566, 90.76 %), 승 (14507, 90.80 %), 광 (14495, 90.85 %), 께 (14411, 90.90 %)
    쳐 (14376, 90.94 %), 존 (14314, 90.99 %), 맞 (14219, 91.03 %), 갔 (14123, 91.08 %)
    테 (13889, 91.12 %), 색 (13887, 91.17 %), 림 (13886, 91.21 %), 억 (13685, 91.25 %)
    떤 (13672, 91.30 %), 찾 (13630, 91.34 %), 써 (13308, 91.38 %), 굴 (13295, 91.42 %)
    황 (13284, 91.47 %), 허 (13220, 91.51 %), 악 (13175, 91.55 %), 글 (13087, 91.59 %)
    쟁 (13036, 91.63 %), 류 (13030, 91.67 %), 락 (12959, 91.72 %), 떠 (12933, 91.76 %)
    항 (12931, 91.80 %), 립 (12919, 91.84 %), 견 (12901, 91.88 %), 볼 (12854, 91.92 %)
    빠 (12830, 91.96 %), 농 (12827, 92.00 %), 희 (12745, 92.04 %), 령 (12685, 92.08 %)
    갖 (12655, 92.12 %), 코 (12649, 92.16 %), 긴 (12647, 92.20 %), 끼 (12632, 92.24 %)
    뿐 (12592, 92.28 %), 접 (12566, 92.32 %), 밖 (12557, 92.36 %), 응 (12549, 92.40 %)
    싶 (12389, 92.44 %), 축 (12370, 92.48 %), 큰 (12337, 92.52 %), 끝 (12093, 92.56 %)
    송 (12007, 92.60 %), 규 (11834, 92.64 %), 카 (11798, 92.67 %), 취 (11703, 92.71 %)
    귀 (11607, 92.75 %), 논 (11586, 92.78 %), 엄 (11580, 92.82 %), 좀 (11524, 92.86 %)
    왜 (11456, 92.89 %), 충 (11334, 92.93 %), 힘 (11016, 92.96 %), 얘 (11011, 93.00 %)
    총 (10972, 93.03 %), 혀 (10932, 93.07 %), 째 (10906, 93.10 %), 몸 (10870, 93.14 %)
    밀 (10749, 93.17 %), 십 (10667, 93.21 %), 답 (10627, 93.24 %), 검 (10570, 93.27 %)
    잠 (10548, 93.31 %), 났 (10528, 93.34 %), 골 (10487, 93.37 %), 떻 (10323, 93.41 %)
    완 (10161, 93.44 %), 돈 (10138, 93.47 %), 몇 (10106, 93.50 %), 럽 (10066, 93.54 %)
    떨 (9725, 93.57 %), 범 (9725, 93.60 %), 꾸 (9705, 93.63 %), 몰 (9654, 93.66 %)
    커 (9641, 93.69 %), 협 (9626, 93.72 %), 높 (9582, 93.75 %), 웃 (9566, 93.78 %)
    넘 (9455, 93.81 %), 익 (9442, 93.84 %), 둘 (9435, 93.87 %), 득 (9426, 93.90 %)
    깨 (9339, 93.93 %), 왕 (9338, 93.96 %), 찰 (9297, 93.99 %), 앉 (9212, 94.02 %)
    량 (9205, 94.05 %), 측 (9172, 94.08 %), 닌 (9135, 94.11 %), 숙 (9058, 94.13 %)
    찬 (9047, 94.16 %), 념 (8967, 94.19 %), 효 (8888, 94.22 %), 돼 (8813, 94.25 %)
    엇 (8809, 94.28 %), 죠 (8777, 94.30 %), 놀 (8760, 94.33 %), 택 (8724, 94.36 %)
    켜 (8709, 94.39 %), 풍 (8669, 94.41 %), 및 (8572, 94.44 %), 붙 (8492, 94.47 %)
    짜 (8448, 94.50 %), 먼 (8403, 94.52 %), 덕 (8332, 94.55 %), 엔 (8315, 94.58 %)
    팔 (8310, 94.60 %), 봉 (8301, 94.63 %), 슨 (8279, 94.65 %), 잖 (8271, 94.68 %)
    큼 (8224, 94.71 %), 혁 (8138, 94.73 %), 됐 (8090, 94.76 %), 뜻 (8068, 94.78 %)
    메 (8022, 94.81 %), 례 (7999, 94.84 %), 싸 (7997, 94.86 %), 밤 (7964, 94.89 %)
    혹 (7859, 94.91 %), 즉 (7822, 94.94 %), 착 (7821, 94.96 %), 패 (7789, 94.99 %)
    풀 (7623, 95.01 %), 층 (7623, 95.03 %), 밝 (7554, 95.06 %), 욱 (7508, 95.08 %)
    욕 (7492, 95.11 %), 베 (7486, 95.13 %), 릴 (7459, 95.15 %), 짓 (7455, 95.18 %)
    폭 (7417, 95.20 %), 탄 (7409, 95.22 %), 율 (7329, 95.25 %), 냥 (7193, 95.27 %)
    칠 (7159, 95.29 %), 티 (7123, 95.32 %), 벽 (7053, 95.34 %), 갑 (7003, 95.36 %)
    봐 (6966, 95.38 %), 틀 (6961, 95.40 %), 므 (6960, 95.43 %), 땅 (6947, 95.45 %)
    슬 (6836, 95.47 %), 삶 (6771, 95.49 %), 획 (6767, 95.51 %), 케 (6627, 95.53 %)
    곡 (6613, 95.55 %), 징 (6601, 95.58 %), 숨 (6582, 95.60 %), 객 (6550, 95.62 %)
    탈 (6520, 95.64 %), 씩 (6508, 95.66 %), 빛 (6503, 95.68 %), 놈 (6452, 95.70 %)
    잔 (6380, 95.72 %), 곧 (6309, 95.74 %), 염 (6248, 95.76 %), 암 (6229, 95.78 %)
    뜨 (6170, 95.80 %), 빨 (6154, 95.82 %), 꽃 (6135, 95.84 %), 흔 (6109, 95.86 %)
    낸 (5971, 95.88 %), 곤 (5966, 95.90 %), 읽 (5959, 95.92 %), 첫 (5934, 95.93 %)
    궁 (5806, 95.95 %), 닥 (5790, 95.97 %), 윤 (5767, 95.99 %), 웠 (5755, 96.01 %)
    넣 (5728, 96.03 %), 끌 (5724, 96.04 %), 척 (5654, 96.06 %), 즘 (5653, 96.08 %)

### 품사 통계

품사에는 MAAG, JKBB, NNGG와 같은 오류가 존재하며, 이를 제외한 품사별 빈도수와 비율은 아래와 같다. 

    NNG: (1289071, 24.771)
    SS: (399854, 7.684)
    EC: (364402, 7.002)
    JKB: (242596, 4.662)
    VV: (229757, 4.415)
    JX: (222579, 4.277)
    SP: (186605, 3.586)
    NNP: (183133, 3.519)
    SF: (177931, 3.419)
    VCP: (165382, 3.178)
    EF: (154166, 2.962)
    EP: (141347, 2.716)
    XSV: (138744, 2.666)
    ETM: (133398, 2.563)
    XSN: (117529, 2.258)
    SN: (115910, 2.227)
    JKO: (113593, 2.183)
    JKG: (92181, 1.771)
    JKS: (89888, 1.727)
    NNB: (88619, 1.703)
    VX: (71021, 1.365)
    JC: (51970, 0.999)
    SH: (50614, 0.973)
    SL: (47596, 0.915)
    ETN: (43460, 0.835)
    XSA: (43413, 0.834)
    VA: (40446, 0.777)
    NR: (26802, 0.515)
    XR: (25908, 0.498)
    MAG: (24866, 0.478)
    SE: (19817, 0.381)
    SW: (19804, 0.381)
    XPN: (18678, 0.359)
    NP: (16059, 0.309)
    JKC: (13788, 0.265)
    MM: (10111, 0.194)
    JKQ: (8794, 0.169)
    SO: (5831, 0.112)
    IC: (5343, 0.103)
    UNA: (2841, 0.055)
    VCN: (2425, 0.047)
    UNT: (2083, 0.040)
    JKV: (2074, 0.040)
    MAJ: (1333, 0.026)
    NA: (1287, 0.025)
    UNC: (661, 0.013)

그 중 명사의 비율은 30.843 % 이다. 


### 명사 길이 통계

대부분 명사의 길이는 5 이하이며, 길이가 1인 명사는 명사 전체 빈도수의 13.54% 이다. 하지만 세종 말뭉치는 복합명사를 단일 명사들로 분해하여 기록하고 있기 때문에 복합명사를 명사로 인정할 경우에는 길이가 좀 더 길어진다.

    length = 1 (217258, 13.544 %)
    length = 2 (996232, 62.106 %)
    length = 3 (283553, 17.677 %)
    length = 4 (76338, 4.759 %)
    length = 5 (18740, 1.168 %)
    length = 6 (6854, 0.427 %)
    length = 7 (2864, 0.179 %)
    length = 8 (1243, 0.077 %)
    length = 9 (549, 0.034 %)
    length = 10 (248, 0.015 %)
    length = 11 (128, 0.008 %)

길이가 11인 명사들의 일부를 확인해 보면 아래와 같다. 

    이십일세기세종전자사전/NNP
    한국여성경영자총연합회/NNP
    다임러크라이슬러코리아/NNP
    전국한약관련학과협의회/NNP
    MCI커뮤니케이션즈사/NNP
    한국여성중소기업인협회/NNP
    남북인간띠잇기대회본부/NNP
    유니벌씨티오브알라바마/NNP
    ...

### 동사/형용사 길이 통계

어미를 제외한 동사의 길이는 아래와 같다. 대부분의 동사가 길이가 4 이하이지만,  동사/형용사는 어미와 함께 쓰이기 때문에 활용이 되는 동사/형용사의 길이는 대부분 2 이상이 된다. 길이가 1인 경우는 '가다/V + ㄴ/E -> 간'과 같이 -ㄴ, -ㄹ 이 결합되는 경우이다. 

    length = 1 (109016, 40.342 %)
    length = 2 (102968, 38.104 %)
    length = 3 (45965, 17.010 %)
    length = 4 (10938, 4.048 %)
    length = 5 (1245, 0.461 %)
    length = 6 (89, 0.033 %)
    length = 7 (2, 0.001 %)
    length = 8 (7, 0.003 %)

길이가 8인 동사들은 아래와 같다. 길이가 긴 동사들은 '조물락조물락' + '거리다'와 같이 거리다/하다/되다/이다 등과 결합되는 동사들이다.

    조물락조물락거리/VV
    오무락조무락거리/VV
    수군덕수군덕거리/VV
    허우적허우적거리/VV
    바스락바스락거리/VV
    으르렁으르렁거리/VV
    엎치락뒤치락거리/VV

[processedfile]: https://drive.google.com/open?id=0B3zCcS70xP4ZTFlyWVF4NFdxYkk
[lr]: https://drive.google.com/open?id=0B3zCcS70xP4ZNnpNTXFIM1hzYW8
[soynlp]: https://github.com/lovit/soynlp
[cbne]: https://github.com/lovit/classifier_based_noun_extractor
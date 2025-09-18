# nbminh2706
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Trang Web Toán Học</title>
    <style>
        :root {
            --primary: #4a6baf;
            --secondary: #ff6b6b;
            --accent: #4ecdc4;
            --dark: #1a1a2e;
            --light: #f8f9fa;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            color: #333;
            line-height: 1.6;
            min-height: 100vh;
        }
        
        header {
            background: linear-gradient(135deg, var(--primary) 0%, var(--dark) 100%);
            color: white;
            padding: 2rem;
            text-align: center;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            border-bottom: 5px solid var(--secondary);
        }
        
        header h1 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
        }
        
        header p {
            font-size: 1.2rem;
            opacity: 0.9;
        }
        
        .container {
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 1.5rem;
        }
        
        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }
        
        .feature {
            background: white;
            border-radius: 10px;
            padding: 2rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }
        
        .feature:hover {
            transform: translateY(-5px);
        }
        
        .feature h3 {
            color: var(--primary);
            margin-bottom: 1rem;
            font-size: 1.5rem;
        }
        
        .feature p {
            margin-bottom: 1.5rem;
            color: #555;
        }
        
        .feature-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: var(--accent);
        }
        
        .input-area {
            margin-bottom: 1rem;
        }
        
        textarea {
            width: 100%;
            padding: 1rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            resize: vertical;
            min-height: 100px;
        }
        
        .upload-btn {
            display: inline-block;
            background: var(--primary);
            color: white;
            padding: 0.8rem 1.5rem;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 0.5rem;
            transition: background 0.3s;
        }
        
        .upload-btn:hover {
            background: #3a559d;
        }
        
        .result-area {
            background: #f8f9fa;
            padding: 1rem;
            border-radius: 5px;
            margin-top: 1rem;
            min-height: 100px;
            border-left: 4px solid var(--accent);
        }
        
        .game-container {
            text-align: center;
        }
        
        .game-board {
            display: grid;
            grid-template-columns: repeat(3, 100px);
            grid-gap: 10px;
            justify-content: center;
            margin: 1.5rem 0;
        }
        
        .game-cell {
            width: 100px;
            height: 100px;
            background-color: #f8f9fa;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            border-radius: 4px;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .game-cell:hover {
            background-color: #e9ecef;
            transform: translateY(-2px);
        }
        
        .tab-container {
            margin-top: 1rem;
        }
        
        .tab-buttons {
            display: flex;
            margin-bottom: 1rem;
            border-bottom: 1px solid #ddd;
        }
        
        .tab-btn {
            padding: 0.8rem 1.5rem;
            background: #f1f1f1;
            border: none;
            cursor: pointer;
            transition: background 0.3s;
        }
        
        .tab-btn.active {
            background: var(--primary);
            color: white;
        }
        
        .tab-content {
            display: none;
        }
        
        .tab-content.active {
            display: block;
        }
        
        footer {
            background-color: var(--dark);
            color: white;
            text-align: center;
            padding: 2rem;
            margin-top: 3rem;
        }
        
        @media (max-width: 768px) {
            .features {
                grid-template-columns: 1fr;
            }
            
            header h1 {
                font-size: 2rem;
            }
            
            .game-board {
                grid-template-columns: repeat(3, 80px);
            }
            
            .game-cell {
                width: 80px;
                height: 80px;
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>Trang Web Toán Học</h1>
        <p>4 Chức Năng Hữu Ích Cho Học Tập</p>
    </header>

    <div class="container">
        <div class="features">
            <div class="feature">
                <div class="feature-icon">🤖</div>
                <h3>Giải Toán bằng AI</h3>
                <p>Tải lên hình ảnh bài toán hoặc mô tả bằng lời, hệ thống AI sẽ giải đáp chi tiết.</p>
                
                <div class="tab-container">
                    <div class="tab-buttons">
                        <button class="tab-btn active" onclick="openTab(event, 'text-tab-1')">Văn bản</button>
                        <button class="tab-btn" onclick="openTab(event, 'image-tab-1')">Hình ảnh</button>
                    </div>
                    
                    <div id="text-tab-1" class="tab-content active">
                        <div class="input-area">
                            <textarea placeholder="Nhập bài toán của bạn..."></textarea>
                        </div>
                    </div>
                    
                    <div id="image-tab-1" class="tab-content">
                        <div class="input-area">
                            <input type="file" id="math-image" accept="image/*" style="display: none;">
                            <button class="upload-btn" onclick="document.getElementById('math-image').click()">Tải Ảnh Lên</button>
                        </div>
                    </div>
                </div>
                
                <button class="upload-btn">Giải Bài Toán</button>
                <div class="result-area">
                    Kết quả sẽ hiển thị ở đây...
                </div>
            </div>

            <div class="feature">
                <div class="feature-icon">✓</div>
                <h3>Kiểm Tra Lỗi Sai</h3>
                <p>Kiểm tra phần trình bày bài làm, phát hiện lỗi sai và gợi ý cách cải thiện.</p>
                
                <div class="tab-container">
                    <div class="tab-buttons">
                        <button class="tab-btn active" onclick="openTab(event, 'text-tab-2')">Văn bản</button>
                        <button class="tab-btn" onclick="openTab(event, 'image-tab-2')">Hình ảnh</button>
                    </div>
                    
                    <div id="text-tab-2" class="tab-content active">
                        <div class="input-area">
                            <textarea placeholder="Nhập bài làm của bạn..."></textarea>
                        </div>
                    </div>
                    
                    <div id="image-tab-2" class="tab-content">
                        <div class="input-area">
                            <input type="file" id="solution-image" accept="image/*" style="display: none;">
                            <button class="upload-btn" onclick="document.getElementById('solution-image').click()">Tải Ảnh Lên</button>
                        </div>
                    </div>
                </div>
                
                <button class="upload-btn">Kiểm Tra Lỗi</button>
                <div class="result-area">
                    Phân tích lỗi sẽ hiển thị ở đây...
                </div>
            </div>

            <div class="feature">
                <div class="feature-icon">📚</div>
                <h3>Tài Liệu Học Tập</h3>
                <p>Yêu cầu tài liệu bạn cần, hệ thống sẽ cung cấp tài nguyên phù hợp.</p>
                <div class="input-area">
                    <textarea placeholder="Bạn cần tài liệu về chủ đề nào?"></textarea>
                </div>
                <button class="upload-btn">Tìm Tài Liệu</button>
                <div class="result-area">
                    <ul>
                        <li><a href="#">Tài liệu Đại số 10</a></li>
                        <li><a href="#">Bài tập Hình học 11</a></li>
                        <li><a href="#">Đề thi Giải tích 12</a></li>
                    </ul>
                </div>
            </div>

            <div class="feature">
                <div class="feature-icon">🎮</div>
                <h3>Trò Chơi & Đề Thi</h3>
                <p>Thử thách bản thân với các trò chơi toán học và đề thi thử.</p>
                <div class="game-container">
                    <p>Chọn trò chơi hoặc đề thi:</p>
                    <select style="padding: 0.5rem; width: 100%; margin: 1rem 0;">
                        <option>Đố vui Toán học</option>
                        <option>Đề thi Đại số 10</option>
                        <option>Đề thi Hình học 11</option>
                        <option>Đề thi Giải tích 12</option>
                    </select>
                    <button class="upload-btn">Bắt Đầu</button>
                    
                    <div class="game-board">
                        <div class="game-cell">5</div>
                        <div class="game-cell">+</div>
                        <div class="game-cell">3</div>
                        <div class="game-cell">×</div>
                        <div class="game-cell">2</div>
                        <div class="game-cell">=</div>
                        <div class="game-cell">?</div>
                        <div class="game-cell">11</div>
                        <div class="game-cell">16</div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <footer>
        <p>Trang Web Toán Học &copy; 2023</p>
    </footer>

    <script>
        // Hàm chuyển đổi tab
        function openTab(evt, tabId) {
            const tabContents = document.getElementsByClassName("tab-content");
            for (let i = 0; i < tabContents.length; i++) {
                tabContents[i].classList.remove("active");
            }
            
            const tabButtons = document.getElementsByClassName("tab-btn");
            for (let i = 0; i < tabButtons.length; i++) {
                tabButtons[i].classList.remove("active");
            }
            
            document.getElementById(tabId).classList.add("active");
            evt.currentTarget.classList.add("active");
        }
        
        // Xử lý tải file ảnh
        document.addEventListener('DOMContentLoaded', function() {
            document.getElementById('math-image').addEventListener('change', function(e) {
                const file = e.target.files[0];
                if (file) {
                    alert(`Đã tải lên ảnh: ${file.name}`);
                }
            });
            
            document.getElementById('solution-image').addEventListener('change', function(e) {
                const file = e.target.files[0];
                if (file) {
                    alert(`Đã tải lên ảnh: ${file.name}`);
                }
            });
            
            // Xử lý trò chơi
            const gameCells = document.querySelectorAll('.game-cell');
            gameCells.forEach(cell => {
                cell.addEventListener('click', function() {
                    this.style.backgroundColor = '#4ecdc4';
                    this.style.color = 'white';
                });
            });
            
            // Xử lý nút giải bài toán
            const solveButtons = document.querySelectorAll('.upload-btn');
            solveButtons.forEach(button => {
                if (button.textContent === 'Giải Bài Toán' || button.textContent === 'Kiểm Tra Lỗi') {
                    button.addEventListener('click', function() {
                        const resultArea = this.nextElementSibling;
                        resultArea.innerHTML = '<p>Đang xử lý... (Tính năng đang được phát triển)</p>';
                        
                        // Mô phỏng xử lý
                        setTimeout(() => {
                            resultArea.innerHTML = `
                                <p><strong>Kết quả phân tích:</strong></p>
                                <p>Hệ thống đã nhận được yêu cầu của bạn. Tính năng này sẽ sớm được tích hợp AI thực tế để xử lý bài toán và cung cấp lời giải chi tiết.</p>
                            `;
                        }, 1500);
                    });
                }
            });
        });
    </script>
</body>
</html>

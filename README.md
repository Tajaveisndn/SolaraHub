do getgenv().AimbotEnabled=false;getgenv().AimbotPart="Head";getgenv().AimbotSmooth=5;getgenv().FOVEnabled=false;getgenv().FOVRadius=1485 -(729 + 706) ;getgenv().FOVColor=Color3.fromRGB(377 -122 ,255,255);getgenv().ESPEnabled=false;getgenv().ESPSettings={Names=false,Boxes=false,Tracers=false,BoxColor=Color3.fromRGB(255,235 + 20 ,255),HeadBorderColor=Color3.fromRGB(1122 -867 ,0 + 0 ,0 -0 ),HeadBorderThickness=1415 -(447 + 966) ,TracerColor=Color3.fromRGB(255,698 -443 ,2072 -(1703 + 114) ),NameColor=Color3.fromRGB(255,956 -(376 + 325) ,417 -162 ),ShowDistance=false};getgenv().IgnoreDead=true;local v9=game:GetService("Players");local v10=game:GetService("RunService");local v11=game:GetService("UserInputService");local v12=game:GetService("TweenService");local v13=workspace.CurrentCamera;local v14=v9.LocalPlayer;local function v15(v40) local v41=0 -0 ;local v42;while true do if (v41==0) then v42=0;while true do if (v42==(1 + 0)) then if (getgenv().IgnoreDead and (v40.Character.Humanoid.Health<=(0 -0))) then return false;end return true;end if (v42==(14 -(9 + 5))) then if ( not v40 or (v40==v14)) then return false;end if ( not v40.Character or  not v40.Character:FindFirstChild("Humanoid")) then return false;end v42=377 -(85 + 291) ;end end break;end end end local function v16(v43) local v44=1265 -(243 + 1022) ;local v45;while true do if (v44==(0 -0)) then local v148=0;while true do if (v148==(1 + 0)) then v44=1181 -(1123 + 57) ;break;end if (v148==(0 + 0)) then v45=v43.Character;if (v45 and v45:FindFirstChild(getgenv().AimbotPart)) then local v220=0;local v221;local v222;local v223;local v224;local v225;while true do if (v220==0) then v221=v45[getgenv().AimbotPart];v222=(v221.Position-v13.CFrame.Position).Unit;v220=1;end if (v220==3) then v225=workspace:Raycast(v13.CFrame.Position,v222 * v223 ,v224);if v225 then return v225.Instance and v225.Instance:IsDescendantOf(v45) ;end break;end if (v220==(255 -(163 + 91))) then v223=(v221.Position-v13.CFrame.Position).Magnitude;v224=RaycastParams.new();v220=1932 -(1869 + 61) ;end if (v220==(1 + 1)) then v224.FilterDescendantsInstances={v14.Character};v224.FilterType=Enum.RaycastFilterType.Blacklist;v220=3;end end end v148=1;end end end if (v44==(1 -0)) then return false;end end end local function v17() local v46=nil;local v47=math.huge;local v48=Vector2.new(v13.ViewportSize.X/2 ,v13.ViewportSize.Y/(1 + 1) );for v126,v127 in pairs(v9:GetPlayers()) do if v15(v127) then local v149=0 -0 ;local v150;while true do if (v149==0) then v150=v127.Character;if (v150 and v150:FindFirstChild(getgenv().AimbotPart)) then local v226=0;local v227;local v228;local v229;while true do if (v226==(0 + 0)) then local v246=0;while true do if (v246==(1475 -(1329 + 145))) then v226=972 -(140 + 831) ;break;end if (v246==(1850 -(1409 + 441))) then v227=v150[getgenv().AimbotPart];v228,v229=v13:WorldToViewportPoint(v227.Position);v246=1;end end end if (1==v226) then if v229 then local v251=718 -(15 + 703) ;local v252;while true do if (v251==(0 + 0)) then v252=(Vector2.new(v228.X,v228.Y) -v48).Magnitude;if ((v252<=getgenv().FOVRadius) and (v252<v47) and v16(v127)) then local v256=438 -(262 + 176) ;while true do if (v256==0) then v46=v127;v47=v252;break;end end end break;end end end break;end end end break;end end end end return v46;end local v18={Drawings={},Connections={}};v18.CreateDrawing=function(v49,v50,v51) local v52=1721 -(345 + 1376) ;local v53;while true do if (v52==1) then return v53;end if (v52==(688 -(198 + 490))) then v53=Drawing.new(v50);for v185,v186 in pairs(v51) do v53[v185]=v186;end v52=4 -3 ;end end end;v18.CreatePlayerESP=function(v54,v55) local v56=0 -0 ;local v57;while true do if (v56==0) then v57={Box=v18:CreateDrawing("Square",{Thickness=1207 -(696 + 510) ,Filled=false,Transparency=1 -0 ,Color=getgenv().ESPSettings.BoxColor,Visible=false}),HeadMarker=v18:CreateDrawing("Circle",{Radius=1272 -(1091 + 171) ,Filled=false,Thickness=getgenv().ESPSettings.HeadBorderThickness,Transparency=1 + 0 ,Color=getgenv().ESPSettings.HeadBorderColor,Visible=false}),Name=v18:CreateDrawing("Text",{Text=v55.Name,Size=40 -27 ,Center=true,Outline=true,Color=getgenv().ESPSettings.NameColor,Visible=false}),Tracer=v18:CreateDrawing("Line",{Thickness=3 -2 ,Transparency=375 -(123 + 251) ,Color=getgenv().ESPSettings.TracerColor,Visible=false}),DistanceText=v18:CreateDrawing("Text",{Text="",Size=64 -51 ,Center=true,Outline=true,Color=Color3.fromRGB(953 -(208 + 490) ,22 + 233 ,114 + 141 ),Visible=false})};v18.Drawings[v55]=v57;break;end end end;v18.RemovePlayerESP=function(v58,v59) if v18.Drawings[v59] then local v145=0;while true do if (v145==(836 -(660 + 176))) then for v196,v197 in pairs(v18.Drawings[v59]) do v197:Remove();end v18.Drawings[v59]=nil;break;end end end end;v18.UpdateESP=function(v60) if  not getgenv().ESPEnabled then local v146=0 + 0 ;while true do if (v146==(202 -(14 + 188))) then for v198,v199 in pairs(v18.Drawings) do for v211,v212 in pairs(v199) do v212.Visible=false;end end return;end end end local v61=v13.CFrame.Position;local v62=v13.ViewportSize;for v128,v129 in pairs(v18.Drawings) do if ( not v128 or  not v128.Character or (v128==v14)) then for v188,v189 in pairs(v129) do v189.Visible=false;end continue;end local v130=v128.Character;local v131=v130:FindFirstChild("HumanoidRootPart");local v132=v130:FindFirstChild("Head");if ( not v131 or  not v132) then local v152=675 -(534 + 141) ;local v153;while true do if (v152==0) then v153=0;while true do if (v153==0) then for v235,v236 in pairs(v129) do v236.Visible=false;end continue;break;end end break;end end end local v133,v134=v13:WorldToViewportPoint(v131.Position);if  not v134 then local v154=0;while true do if (v154==(0 + 0)) then for v214,v215 in pairs(v129) do v215.Visible=false;end continue;break;end end end local v135=(v61-v131.Position).Magnitude;if (v135>(885 + 115)) then local v155=0 + 0 ;while true do if (v155==(0 -0)) then for v217,v218 in pairs(v129) do v218.Visible=false;end continue;break;end end end if getgenv().ESPSettings.Boxes then local v156=0 -0 ;local v157;local v158;local v159;local v160;local v161;while true do if (v156==(5 -3)) then v161=Vector2.new(v157.X-(v160.X/2) ,v157.Y-(v160.Y/(2 + 0)) );v129.Box.Size=v160;v156=3;end if (v156==(2 + 1)) then v129.Box.Position=v161;v129.Box.Visible=true;v156=400 -(115 + 281) ;end if (v156==(9 -5)) then v129.Box.Color=getgenv().ESPSettings.BoxColor;break;end if (v156==(1 + 0)) then v159=v13:WorldToViewportPoint(v131.Position-Vector3.new(0 -0 ,10 -7 ,867 -(550 + 317) ) );v160=Vector2.new((v158.Y-v159.Y)/(2 -0) ,v158.Y-v159.Y );v156=2;end if (v156==(0 -0)) then v157=v13:WorldToViewportPoint(v131.Position);v158=v13:WorldToViewportPoint(v132.Position + Vector3.new(0,0.5,0 -0 ) );v156=1;end end else v129.Box.Visible=false;end local v136=v13:WorldToViewportPoint(v132.Position);v129.HeadMarker.Position=Vector2.new(v136.X,v136.Y);v129.HeadMarker.Radius=math.clamp(500/v135 ,290 -(134 + 151) ,1675 -(970 + 695) );v129.HeadMarker.Visible=true;if getgenv().ESPSettings.Names then local v163=0 -0 ;while true do if (v163==0) then v129.Name.Position=Vector2.new(v133.X,v133.Y-40 );v129.Name.Visible=true;break;end end else v129.Name.Visible=false;end if getgenv().ESPSettings.Tracers then local v165=0;while true do if (v165==(1990 -(582 + 1408))) then v129.Tracer.From=Vector2.new(v62.X/(6 -4) ,v62.Y);v129.Tracer.To=Vector2.new(v133.X,v133.Y);v165=1;end if (v165==(1 -0)) then v129.Tracer.Visible=true;break;end end else v129.Tracer.Visible=false;end if getgenv().ESPSettings.ShowDistance then local v167=0 -0 ;local v168;while true do if (v167==0) then v168=0;while true do if (v168==(1825 -(1195 + 629))) then v129.DistanceText.Visible=true;break;end if ((0 -0)==v168) then v129.DistanceText.Text=string.format("%.0f m",v135);v129.DistanceText.Position=Vector2.new(v133.X,v133.Y + (276 -(187 + 54)) );v168=781 -(162 + 618) ;end end break;end end else v129.DistanceText.Visible=false;end end end;local v23=Drawing.new("Circle");v23.Visible=getgenv().FOVEnabled;v23.Radius=getgenv().FOVRadius;v23.Color=getgenv().FOVColor;v23.Thickness=1;v23.Filled=false;v23.Transparency=1 + 0 ;v23.Position=Vector2.new(v13.ViewportSize.X/(2 + 0) ,v13.ViewportSize.Y/(3 -1) );local v31=loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))();local v32=v31.CreateLib("Solara Hub 1.0","Ocean");local v33=false;local v34=v32:NewTab("Combat");local v35=v34:NewSection("Aimbot Settings");v35:NewToggle("Enable Aimbot","Liga/Desliga o aimbot",function(v63) getgenv().AimbotEnabled=v63;end);v35:NewDropdown("Aimbot Part","Escolha a parte para mirar",{"Head","HumanoidRootPart"},function(v65) getgenv().AimbotPart=v65;end);v35:NewToggle("FOV Circle","Mostra/Esconde o círculo",function(v67) local v68=0;while true do if (v68==(1636 -(1373 + 263))) then getgenv().FOVEnabled=v67;v23.Visible=v67;break;end end end);v35:NewSlider("FOV Size","Ajusta o tamanho do FOV",1500 -(451 + 549) ,16 + 34 ,function(v69) local v70=0;while true do if (v70==0) then getgenv().FOVRadius=v69;v23.Radius=v69;break;end end end);v35:NewSlider("Aimbot Smoothness","Ajusta a suavidade do aimbot",31 -11 ,1,function(v71) getgenv().AimbotSmooth=v71;end);local v36=v32:NewTab("ESP");local v37=v36:NewSection("ESP Settings");v37:NewToggle("Enable ESP","Liga/Desliga o ESP",function(v73) getgenv().ESPEnabled=v73;end);v37:NewToggle("Show Names","Mostra nomes dos jogadores",function(v75) getgenv().ESPSettings.Names=v75;end);v37:NewToggle("Show Boxes","Mostra caixas ao redor dos jogadores",function(v77) getgenv().ESPSettings.Boxes=v77;end);v37:NewToggle("Show Tracers","Mostra linhas até os jogadores",function(v79) getgenv().ESPSettings.Tracers=v79;end);v37:NewToggle("Show Distance","Mostra distância dos jogadores",function(v81) getgenv().ESPSettings.ShowDistance=v81;end);v37:NewColorPicker("Box Color","Escolha a cor das caixas",Color3.fromRGB(255,428 -173 ,255),function(v83) getgenv().ESPSettings.BoxColor=v83;end);v37:NewColorPicker("Head Border Color","Escolha a cor das bordas da cabeça",Color3.fromRGB(1639 -(746 + 638) ,0 + 0 ,0 -0 ),function(v85) getgenv().ESPSettings.HeadBorderColor=v85;end);v37:NewSlider("Head Border Thickness","Ajuste a espessura da borda da cabeça",346 -(218 + 123) ,1582 -(1535 + 46) ,function(v87) getgenv().ESPSettings.HeadBorderThickness=v87;end);local v38=v32:NewTab("Settings");local v39=v38:NewSection("UI Settings");v39:NewButton("Minimizar Interface","Minimiza o painel para um quadrado",function() if  not v33 then local v147=0 + 0 ;while true do if (v147==1) then CreateMinimizedButton();break;end if (0==v147) then v31:ToggleUI();v33=true;v147=1;end end end end);function CreateMinimizedButton() if game.Players.LocalPlayer.PlayerGui:FindFirstChild("MinimizedButton") then return;end local v89=Instance.new("ScreenGui");v89.Name="MinimizedButton";v89.Parent=game.Players.LocalPlayer:WaitForChild("PlayerGui");v89.ZIndexBehavior=Enum.ZIndexBehavior.Sibling;local v94=Instance.new("TextButton");v94.Name="MinimizeSquare";v94.Size=UDim2.new(0,100,0 + 0 ,600 -(306 + 254) );v94.Position=UDim2.new(0 + 0 ,19 -9 ,1467.5 -(899 + 568) , -(14 + 6));v94.BackgroundColor3=Color3.fromRGB(72 -42 ,633 -(268 + 335) ,320 -(60 + 230) );v94.BorderSizePixel=572 -(426 + 146) ;v94.BackgroundTransparency=0 + 0 ;v94.AnchorPoint=Vector2.new(1456 -(282 + 1174) ,811.5 -(569 + 242) );v94.Text="Solara";v94.Font=Enum.Font.GothamSemibold;v94.TextSize=16;v94.TextColor3=Color3.fromRGB(734 -479 ,0,0 + 0 );v94.TextStrokeTransparency=1;v94.TextXAlignment=Enum.TextXAlignment.Center;v94.TextYAlignment=Enum.TextYAlignment.Center;v94.Parent=v89;local v113=Instance.new("UICorner");v113.CornerRadius=UDim.new(1024.2 -(706 + 318) ,1251 -(721 + 530) );v113.Parent=v94;local v116=false;local v117,v118,v119;v94.InputBegan:Connect(function(v140) if (v140.UserInputType==Enum.UserInputType.MouseButton1) then local v174=1271 -(945 + 326) ;local v175;while true do if (v174==(0 -0)) then v175=0 + 0 ;while true do if ((700 -(271 + 429))==v175) then v116=true;v118=v140.Position;v175=1;end if ((1 + 0)==v175) then v119=v94.Position;v140.Changed:Connect(function() if (v140.UserInputState==Enum.UserInputState.End) then v116=false;end end);break;end end break;end end end end);v94.InputChanged:Connect(function(v141) if (v141.UserInputType==Enum.UserInputType.MouseMovement) then v117=v141;end end);v11.InputChanged:Connect(function(v142) if ((v142==v117) and v116) then local v176=1500 -(1408 + 92) ;local v177;local v178;local v179;while true do if (v176==(1086 -(461 + 625))) then v177=0;v178=nil;v176=1289 -(993 + 295) ;end if (v176==(1 + 0)) then v179=nil;while true do if (0==v177) then v178=v142.Position-v118 ;v179=UDim2.new(1171 -(418 + 753) ,math.clamp(v119.X.Offset + v178.X ,0 + 0 ,v13.ViewportSize.X-v94.Size.X.Offset ),0 + 0 ,math.clamp(v119.Y.Offset + v178.Y ,0 + 0 ,v13.ViewportSize.Y-v94.Size.Y.Offset ));v177=1 + 0 ;end if ((530 -(406 + 123))==v177) then v12:Create(v94,TweenInfo.new(1769.1 -(1749 + 20) ,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),{Position=v179}):Play();break;end end break;end end end end);v94.MouseButton1Click:Connect(function() local v143=0 + 0 ;local v144;while true do if (v143==(1322 -(1249 + 73))) then v144=0 + 0 ;while true do if (v144==(1146 -(466 + 679))) then v33=false;v31:ToggleUI();break;end if (v144==0) then if v116 then return;end v89:Destroy();v144=1;end end break;end end end);local v120=0 -0 ;v10.RenderStepped:Connect(function() if (v89 and v89:FindFirstChild("MinimizeSquare")) then local v180=0;local v181;while true do if (v180==(2 -1)) then v94.TextColor3=v181;break;end if (v180==(1900 -(106 + 1794))) then v120=(v120 + 1 + 0)%(92 + 268) ;v181=Color3.fromHSV(v120/360 ,1,1);v180=2 -1 ;end end end end);end v9.PlayerAdded:Connect(function(v121) v18:CreatePlayerESP(v121);end);v9.PlayerRemoving:Connect(function(v122) v18:RemovePlayerESP(v122);end);for v123,v124 in ipairs(v9:GetPlayers()) do if (v124~=v14) then v18:CreatePlayerESP(v124);end end v10.RenderStepped:Connect(function() local v125=0 -0 ;while true do if (v125==(114 -(4 + 110))) then v23.Position=Vector2.new(v13.ViewportSize.X/(586 -(57 + 527)) ,v13.ViewportSize.Y/2 );v23.Visible=getgenv().FOVEnabled;v125=1;end if (v125==(1428 -(41 + 1386))) then v18:UpdateESP();if getgenv().AimbotEnabled then local v192=103 -(17 + 86) ;local v193;while true do if (v192==0) then v193=v17();if (v193 and v193.Character and v193.Character:FindFirstChild(getgenv().AimbotPart)) then local v238=v193.Character[getgenv().AimbotPart];local v239=v13:WorldToViewportPoint(v238.Position);if (v239.Z>(0 + 0)) then local v247=0 -0 ;local v248;local v249;local v250;while true do if (v247==(2 -1)) then v250=(v248-v249)/getgenv().AimbotSmooth ;v13.CFrame=v13.CFrame:Lerp(CFrame.new(v13.CFrame.Position,v238.Position),1 -(getgenv().AimbotSmooth/20) );break;end if (v247==0) then v248=Vector2.new(v239.X,v239.Y);v249=Vector2.new(v13.ViewportSize.X/(168 -(122 + 44)) ,v13.ViewportSize.Y/(2 -0) );v247=3 -2 ;end end end end break;end end end break;end end end); end

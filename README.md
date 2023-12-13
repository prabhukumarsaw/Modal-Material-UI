# Modal-Material-UI
How to use multiple material ui dialog with React?

# App.Js
<code>
function App() {
  const [darkMode, setDarkMode] = useState(true);
  
  const [openLogin, setOpenLogin] = useState(false);  //1----


  return (
    <ThemeProvider theme={darkMode ? darkTheme : lightTheme}>
      <Router >
        <Navbar />
        <Body>
          <HeroSection />
          <Wrapper>
             {/* <About />  */}
             
          </Wrapper>
          <Footer onClickLogin={() => setOpenLogin(true)}/>  //2-----
          
          <Dashboard open={openLogin} handleClose={() => setOpenLogin(false)} />  //3-----
          
          
        </Body>
      </Router>
    </ThemeProvider>
  );
}

export default App;

  
  </code>


  # Footer.js

  <code>
    
  function Footer({onClickLogin}) { //4--------


  return (
    <FooterContainer>
      <FooterWrapper>
        <Logo>text</Logo>
        <Nav>
          <NavLink href="#about">About</NavLink>
          <NavLink href="#projects">Portfolio</NavLink>
          <button onClick={onClickLogin}> //5---------
          Login
        </button>
          

          
        </Nav>
        <SocialMediaIcons>
          <SocialMediaIcon href={Bio.facebook} target="display"><FacebookIcon /></SocialMediaIcon>
          <SocialMediaIcon href={Bio.twitter} target="display"><TwitterIcon /></SocialMediaIcon>
          <SocialMediaIcon href={Bio.linkedin} target="display"><LinkedInIcon /></SocialMediaIcon>
          <SocialMediaIcon href={Bio.insta} target="display"><InstagramIcon /></SocialMediaIcon>
        </SocialMediaIcons>
        <Copyright>
          &copy; 2023 text. All rights reserved.
        </Copyright>

      </FooterWrapper>
    </FooterContainer>
  );
}

export default Footer;
  
  </code>

  # Modal.js
prerequest
- import { CloseRounded, GitHub, LinkedIn } from '@mui/icons-material';
- import { Modal } from '@mui/material';
- import React from 'react'
- import styled from 'styled-components'

  <code>

  const index = ({ open, handleClose }) => {
    return (
        <Modal   open={open} onClose={handleClose}>
            <Container>
                <Wrapper>
                    <CloseRounded
                        style={{
                            position: "absolute",
                            top: "10px",
                            right: "20px",
                            cursor: "pointer",
                        }}
                        onClick={() => handleClose({ state: false, project: null })}
                    />
                    
                    <Title>Success key</Title>
                    <Date>15 dec</Date>
                    
                    <Desc>Try something new</Desc>
                    
                    <ButtonGroup>
                        <Button target='new'>View Code</Button>
                        <Button  target='new'>View Live App</Button>
                    </ButtonGroup>
                </Wrapper>
            </Container>

        </Modal>
    )
}

export default index

   </code>
